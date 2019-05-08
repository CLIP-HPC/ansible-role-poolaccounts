Role Name
=========

Create pool accounts for WLCG Site.


Role Variables
--------------

Prefix for the home directory

    poolaccounts_homedir: /home

A list of hashes decribing the pool poolaccount.
A hash can describe a list of users or a single user

    poolaccounts:
      - name: 'cms%d.d3'
        uid: 10000
        number: 100
        step: 2
        description: 'Standard User of the CMS VO'
        grp: cms
        gid: 10000
      - name: 'cmssgm'
        uid: 11000
        description: 'SW User of the CMS VO'
        grp: cmsprd
        gid: 11000
        groups: cms


Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in
regards to parameters that may need to be set for other roles, or variables that
are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: hephyvienna.poolaccounts
           vars:
             poolaccounts:
               - name: 'cms%d.d3'
                 uid: 10000
                 number: 100
                 comment: 'Standard User of the CMS VO'
                 group: cms
                 gid: 10000
               - name: 'cmsprd%d.d3'
                 uid: 11000
                 number: 10
                 comment: 'Production User of the CMS VO'
                 group: cmsprd
                 gid: 11000
                 groups: cms
               - name: 'cmspil%d.d3'
                 uid: 12000
                 number: 10
                 comment: 'Pilot User of the CMS VO'
                 group: cmspil
                 gid: 10000
                 groups: cms
               - name: 'cmssgm'
                 uid: 13000
                 comment: 'SW User of the CMS VO'
                 group: cmssgm
                 gid: 11000
                 groups: cms

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a
website (HTML is not allowed).
