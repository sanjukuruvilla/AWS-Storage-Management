# AWS Storage Management for EC2 Instances

This repository provides instructions for adding additional storage in EC2 Linux instances on AWS.

## Overview

This guide walks you through the process of attaching additional storage to an EC2 instance on AWS, partitioning it, and allocating storage space to multiple users.

## Table of Contents

1. [Task Description](#task-description)
2. [Phase 1: Partitioning and Allocation](#phase-1-partitioning-and-allocation)
3. [Phase 2: Adding Storage for Additional User](#phase-2-adding-storage-for-additional-user)
4. [Storage Management](#storage-management)
5. [Usage](#usage)
6. [Additional Documentation](#additional-documentation)
7. [Contributing](#contributing)
8. [License](#license)

## Task Description

You have an instance with 8GB storage and need to create directories for two users, allocating 6GB each, while ensuring isolation and ease of access.

## Phase 1: Partitioning and Allocation

1. Attach a 12GB EBS volume to the instance.
2. Partition the volume into two partitions, each with 6GB storage.
3. Create physical volumes (PVs) for both partitions.
4. Create a volume group (VG) and add the PVs to it.
5. Create logical volumes (LVs) for each user (e.g., Kiran and Ted) with 6GB storage.
6. Mount the logical volumes at `/kiran` and `/ted`.

## Phase 2: Adding Storage for Additional User

1. Mike requires an additional 2GB for storing large files.
2. Attach another 2GB volume and repeat the partitioning process.
3. Extend the volume group (VG) to include the new PV.
4. Mount the 2GB volume at `/Home/Mike/Backup`.

## Storage Management

- Use `df -h` to view storage details.
- Edit `/etc/fstab` to make storage mounts permanent.

## Usage

Follow the provided instructions to manage storage on AWS EC2 instances. Ensure proper allocation and isolation of storage space for users.

## Additional Documentation

For more detailed instructions and best practices, please refer to the [documentation folder](documentation/) in this repository.

## Contributing

Contributions to this repository are welcome! If you find issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
