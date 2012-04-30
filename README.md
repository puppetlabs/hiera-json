What?
-----

A JSON backend for Hiera

Configuration?
--------------

A sample Hiera config file that activates this backend and stores
data in _/etc/puppet/hieradata_ can be seen below:

<pre>
---
:backends: json
:hierarchy: %{location}
            common
:json:
   :datadir: /etc/puppet/hieradata
</pre>

Support
-------

Please log tickets and issues at our [Projects site](http://projects.puppetlabs.com)
