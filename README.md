lebedevdsl.carbonzipper
=========

Installs/configures carbonzipper

Requirements
------------

None

Role Variables
--------------

Name | type | default | description
---|---|---|---
carbonzipper_package | string | carbonzipper | carbonzipper package name
carbonzipper_config | string | "/etc/carbonzipper/carbonzipper.conf" | carbonzipper config file location
carbonzipper_listen | string | 'localhost:8088' | Carbonzipper listen host:port
carbonzipper_max_procs | int | 0 | Maximum processes
carbonzipper_graphite_interval | string | '60s' | Graphite metrics push interval
carbonzipper_graphite_prefix | string | 'carbon.zipper' | Graphite metrics prefix for zipper
carbonzipper_buckets | int | 10 | Buckets for request duration metrics count
carbonzipper_timeouts_global | string | "10s" | Carbonzipper global timeout
carbonzipper_timeouts_after_started | string | "2s" | Carbonzipper timeout after start
carbonzipper_concurrency_limit | int | 0 | max thread concurrency
carbonzipper_max_idle_conns_per_host | int | 100 | Maximum idle connections pool
carbonzipper_expire_delay_sec | int | 10 | Carbonzipper cache expiry
carbonzipper_graphite_09_compat | string | 'false' | Compatibility mode for graphite 0.9
carbonzipper_backends | list of strings | ["http://localhost:8083"] | URLS of carbonservers
carbonzipper_logger | list of objects | [{logger: "", file:"/var/log/carbonzipper/carbonzipper.log", level:"error", encoding: "json"}] | Logger objects

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: lebedevdsl.carbonzipper, become: yes }
