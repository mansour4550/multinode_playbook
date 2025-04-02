# Ansible Multi-Node Apache Atlas Setup

This repository contains an Ansible playbook to automate the installation and configuration of Apache Atlas on a multi-node cluster. The setup integrates Atlas with pre-installed Kafka, HBase, and Solr.

## Cluster Overview
- **master1 (192.168.22.10)**: Primary Atlas server node, also hosts Solr.
- **master2 (192.168.22.11)**: Secondary Atlas server node (for HA).
- **master3 (192.168.22.16)**: Hosts ZooKeeper quorum member.
- **slave2 (192.168.22.14)**: Hosts Kafka.
- **edge1 (192.168.22.17)**: Optional edge node for Hive/Sqoop clients or Atlas UI access.

## Prerequisites
- Kafka, HBase, and Solr must be pre-installed.
- SSH access for the `hadoopZetta` user on all nodes.
- Ansible installed on the control node.

## Usage
1. Update `inventory.yml` with your cluster IPs.
2. Run the playbook:
   ```bash
   ansible-playbook -i inventory.yml playbook.yml
