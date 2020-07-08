# awls
Simple tool to lookup EC2 instance information in your shell

## Usage

```
$ awls -h
usage: awls [-h] [--profile PROFILE] [--region REGION] [--type TYPE] [N]

Interrogate AWS EC2 and return pretty data

positional arguments:
  N                     Search query

optional arguments:
  -h, --help            show this help message and exit
  --profile PROFILE, -p PROFILE
                        Which AWS profile to use
  --region REGION, -r REGION
                        Which AWS region to use
  --type TYPE, -t TYPE  Which instance type
```

## Example Usage

```
# Search for a specific query
./awls test -p AWS_PROFILE -r eu-central-1

# Output
+---------------------------+---------+--------+---------------------+---------------+----------------+-----------+--------------+---------+
| Launched At               | State   | Name   | Instance ID         | Private IP    | Public IP      | Type      | Key Name     | Owner   |
|---------------------------+---------+--------+---------------------+---------------+----------------+-----------+--------------+---------|
| 2020-03-09 18:11:11+00:00 | running |        | i-0e723817f6870e680 | 172.31.3.131  | 34.211.145.241 | t2.medium | MyOtherKey   | hml     |
| 2019-08-14 18:54:44+00:00 | running |        | i-04a317cebc30e0e08 | 172.31.25.152 | 34.213.136.121 | t2.micro  | MyKeyPair    | hml     |
+---------------------------+---------+--------+---------------------+---------------+----------------+-----------+--------------+---------+
```

## Setting default profile
If you wish to set a default AWS profile you can edit the parser profile default line `default=""` 
