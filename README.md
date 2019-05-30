# poolaccounts

Create pool accounts for WLCG/EGI Grid Site


## Role Variables

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

A list of hashes describing the poolaccounts.
A entry can describe a list of users or a single user (see example).


    poolaccounts_homedir: /home

Prefix for the home directory


## Example Playbook

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

Written by [Dietrich Liko](http://hephy.at/dliko) in April 2019

[Institute for High Energy Physics](http://www.hephy.at) of the
[Austrian Academy of Sciences](http://www.oeaw.ac.at)
