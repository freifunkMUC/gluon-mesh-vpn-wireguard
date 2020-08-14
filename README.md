# gluon-mesh-vpn-wireguard

You can use this package for connecting with wireguard to the Freifunk Munich network.

You should use something like the following in the site.conf:

        
```
 mesh_vpn = {
        mtu = 1410,
        wireguard = {
                enabled = 'true',
                iface = 'mesh-vpn',
                limit = '1', -- actually unused
                mcastgroup = 'ff02::15c',
                peers = {
                                {
                                        publickey ='N9uF5Gg1B5AqWrE9IuvDgzmQePhqhb8Em/HrRpAdnlY=',
                                        endpoint ='ffkwsn01.freifunk-koenigswinter.de:30020',
                                        link_address = 'fe80::f000:22ff:fe12:01',
                                },                
                                {
                                        publickey ='liatbdT62FbPiDPHKBqXVzrEo6hc5oO5tmEKDMhMTlU=',
                                        endpoint ='ffkwsn02.freifunk-koenigswinter.de:30020',
                                        link_address = 'fe80::f000:22ff:fe12:02',
                                },
                                {
                                        publickey ='xakSGG39D1v90j3Z9eVWzojh6nDbnsVUc/RByVdcKB0=',
                                        endpoint ='ffkwsn03.freifunk-koenigswinter.de:30020',
                                        link_address = 'fe80::f000:22ff:fe12:07',
                                },

                        },
        },
        
```    

**The `mcastgroup` is the one of the server(s)!**

And you should include the package in the site.mk of course!
