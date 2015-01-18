Ospfd can't export the default gateway via route label because
get_rtaddrs gets confused by a netmask (RTAX_NETMASK) of 0 because
sa->sa_len in get_rtaddrs() is 0 and ROUNDUP then returns 0 also.

The bug has been fixed in ospf6d in the same way a couple of years ago.
Ospf6d uses the ROUNDUP macro from route/show.c now.
ospfd should do the same.
