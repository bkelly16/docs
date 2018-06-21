# Security Enhanced Linux

{{:selinux_flow_chart.png|}}

## Introduction


Security-Enhanced Linux (SELinux) is a mandatory access control (MAC) security mechanism implemented in the kernel.
SELinux controls access between applications and resources.(resources refer to system processes and files).\\
SELinux follows the model of least-privilege. By default everything is denied and then a series of exceptions policies are written that give each element of the system (a service, program or user) only the access required to function. If a service, program or user subsequently tries to access or modify a file or resource not necessary for it to function, then access is denied and the action is logged.\\
For Example: A user's mail files should be readable only by that user, but the mail client software has the ability to change them to be world readable. By implementing SELinux correctly, the system will deny access when the client tries to access any other mail that is not owned by the user.\\ 

SELinux is not a firewall. A firewall controls the flow of traffic to and from a computer to the network. SELinux can confine access of programs within a computer and hence can be conceptually thought of a internal firewall between programs.\\

SELinux has 3 modes of operation:\\

**Enforcing** - The default mode which will enable and enforce the SELinux security policy on the system.\\
**Permissive** - SELinux is enabled but will not enforce the security policy, only warn and log actions.\\
**Disabled** - SELinux is not running.

#### Mandatory Access Control

Mandatory access control (MAC) refers to a type of access control by which the operating system constrains the ability of a subject or initiator to access or generally perform some sort of operation on an object or target. In practice, a subject is usually a process or thread; objects are constructs such as files, directories, TCP/UDP ports, shared memory segments, IO devices etc. Subjects and objects each have a set of security attributes. Whenever a subject attempts to access an object, an authorization rule enforced by the operating system kernel examines these security attributes and decides whether the access can take place. Any operation by any subject on any object is tested against the set of authorization rules (aka policy) to determine if the operation is allowed. A database management system, in its access control mechanism, can also apply mandatory access control; in this case, the objects are tables, views, procedures, etc.

#### Discretionary Access Control

In computer security, discretionary access control (DAC) is a type of access control defined by the Trusted Computer System Evaluation Criteria[1] "as a means of restricting access to objects based on the identity of subjects and/or groups to which they belong. The controls are discretionary in the sense that a subject with a certain access permission is capable of passing that permission (perhaps indirectly) on to any other subject (unless restrained by mandatory access control)".

Discretionary access control is commonly discussed in contrast to mandatory access control (MAC, sometimes termed non-discretionary access control). Occasionally a system as a whole is said to have "discretionary" or "purely discretionary" access control as a way of saying that the system lacks mandatory access control. On the other hand, systems can be said to implement both MAC and DAC simultaneously, where DAC refers to one category of access controls that subjects can transfer among each other, and MAC refers to a second category of access controls that imposes constraints upon the first.

## Context



 A security context, or security label, is the mechanism used by SELinux to classify resources, such as processes and files (subjects and objects).This context allows SELinux to enforce rules for how and by whom a given resource should be accessed. The security context is comprised of four fields: user, role, type, and level. All fields are required, except for the level.

#### User Field

The first component of the security context is the "SELinux User" component. This component can be thought of as a way of grouping roles. SELinux Users can have multiple roles that they can reach, and then in those roles they can reach multiple types. Three users that you will usually see on the system are "user_u", "system_u" and root.

#### Role Field

This field is only really relevant on processes or domains. The role field on a file is always object_r, and really has no meaning other than as a place holder. On a process you would usually see a role like system_r or sysadm_r. Roles are used to group security types. So you can specify in policy which roles are able to execute which types.
Examples of roles include: an unprivileged user, a web administrator, and a database administrator.

#### Type Field

This is the heart of SELinux Type Enforcement. Most of the policy rules in SELinux revolve around what subject types have what access to which object types. 
A type is a way of grouping items based on their similarity from a security perspective. This is not necessarily related to the unique purpose of an application or the content of a document. For example, a file can have any type of content and be for any purpose, but if it belongs to a user and exists in that user's home directory, it is considered to be of a specific security type, user_home_t.


## Policy & Access Control

The SELinux Policy is the set of rules that guide the SELinux security engine. It defines types for file objects and domains for processes. It uses roles to limit the domains that can be entered, and has user identities to specify the roles that can be attained. In essence, types and domains are equivalent, the difference being that types apply to objects while domains apply to processes.

The policy defines various rules that say how each domain may access each type. Only what is specifically allowed by the rules is permitted.


The default policy for Centos is the targeted policy, which is highly configurable.Under the targeted policy, every subject and object runs in the unconfined_t domain except for the specific targeted daemons. Objects that are in the unconfined_t domain have no restrictions and fall back to using standard Linux security, that is, DAC.

#### Example:

All processes and files have an SELinux security context. Let's see these in action by looking at the SELinux security context of the Apache homepage: '/var/www/html/index.html'

	
	$ ls -Z /var/www/html/index.html  
	-rw-r--r--  username username system_u:object_r:httpd_sys_content_t /var/www/html/index.html

In addition to the standard file permissions and ownership, we can see the SELinux security context fields:\\ system_u:object_r:httpd_sys_content_t.\\
This is based upon user:role:type:mls. In our example above, user:role:type fields are displayed and mls is hidden. Within the default targeted policy, type is the important field used to implement Type Enforcement, in this case httpd_sys_content_t.\\

Now consider the SELinux security context of the Apache web server process: 'httpd'\\

	
	$ ps axZ | grep httpd
	system_u:system_r:httpd_t        3234 ?        Ss     0:00 /usr/sbin/httpd


Here we see the from the type field that Apache is running under the httpd_t type domain.

Finally, let's look at the SELinux security context of a file in our home directory:

	
	$ ls -Z /home/username/myfile.txt
	-rw-r--r--  username username user_u:object_r:user_home_t      /home/username/myfile.txt


where we see the type is user_home_t, the default type for files in a user's home directory.

Access is only allowed between similar types, so Apache running as httpd_t can read /var/www/html/index.html of type httpd_sys_content_t. Because Apache runs in the httpd_t domain and does not have the userid:username, it can not access /home/username/myfile.txt even though this file is world readable because /home/username/myfile.txt SELinux security context is not of type httpd_t. If Apache were to be exploited, assuming for the sake of this example that the root account right needed to effect a SELinux re-labeling into another context were not obtained, it would not be able to start any process not in the httpd_t domain (which prevents escalation of privileges) or access any file not in an httpd_t related domain.

## Booleans

Booleans are specific rules within the policy. This is where we set the on/off rules for a certain policy. Who can access, write, delete, etc. can be configured here.


## SELinux with Samba & Webmin

Currently setting up a series of samba shares in the Lab using Webmin as an interface. We are trying to make a similar system to our main file server for testing.

## Sources

http://selinuxproject.org/page/Main_Page

http://wiki.centos.org/HowTos/SELinux
