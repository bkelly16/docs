# Ceph Recovery

Speed up backfilling speed. If you see lots of backfill_wait in the status of your pools check if the output "ceph --show-config | grep osd_max_backfill" is eqaul to 1.

If so you can speed up recovery with:

    ceph tell osd.* injectargs '--osd_max_backfills=10'

Becaeful as this can severly impact client IO. A small trickle recovery is by deisgn over opening the flood gates. The above commadn will en the flood gates.

You cannot immediatly set this option back either. Once a pg starts backfill it has to complete.
