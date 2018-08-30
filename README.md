# Ansible Role: ArangoDB


An Ansible Role that installs arangodb on  Debian/Ubuntu Linux.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    arangodb_autoupgrade: false
    arangodb_restart_sleep: 10
    arangodb_database_directory: '/var/lib/arangodb'
    arangodb_database_maximaljournalsize: 33554432
    arangodb_server_endpoints:
      - 'tcp://0.0.0.0:8528'

    arangodb_server_reuseaddress: 'false'
    arangodb_server_disableauthentication: 'yes'
    arangodb_server_threads: 4
    arangodb_scheduler_threads: 1
    arangodb_javascript_startupdirectory: '/usr/share/arangodb/js'
    arangodb_javascript_apppath:          '/var/lib/arangodb-apps'
    arangodb_javascript_v8contexts:       5
    arangodb_log_level:    'info'
    arangodb_log_severity: 'human'
    arangodb_log_file:     '/var/log/arangodb/arangod.log'
    arangodb_cluster_disabledispatcherkickstarter: 'yes'
    arangodb_cluster_disabledispatcherfrontend:    'yes'
    arangodb_cluster_datapath:                     '/var/lib/arangodb/cluster'
    arangodb_cluster_logpath:                      '/var/log/arangodb/cluster'
    arangodb_cluster_agentpath:                    '/usr/lib/arangodb/etcd-arango'
    arangodb_cluster_arangodpath:                  '/usr/sbin/arangod'
    arangodb_cluster_dbserverconfig:               '/etc/arangodb/arangod.conf'
    arangodb_cluster_coordinatorconfig:            '/etc/arangodb/arangod.conf'


## Dependencies

None.

## Example Playbook

    - hosts: all
      become: True
      gather_facts: True
      roles:
        - arangodb

## Example inventory
    
    [arangodb]
    <ip_address_server_1>
    <ip_address_server_2>
    <ip_address_server_3>

    [coordinator]
    <ip_address_server_1>

    [primary]
    <ip_address_server_2>

    [secondary]
    <ip_address_server_3>


## License

MIT / BSD

## Author Information

This role was created in 2018 by [UniCode].
