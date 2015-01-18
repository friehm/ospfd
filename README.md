On a router with only one ospf speaking interface, the link on this
interface goes down. The ospfd notice that, but doesn't generate
a router lsa for itself, because nlinks is zero. So the router doesn't
realize that it can not reach learned ospf routes anymore. The routes
get not deleted from the kernel routing table.

Sometimes I have also seen multiple times the same ospf routes inside
the kernel routing table, after the interface went up again. But this
is not reproducable all the time.
