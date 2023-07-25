# secretsdump.py

## Description

This is a customized version of the `secretsdump.py` script from the `impacket` Python library. It allows the extraction of secrets (NTDS.dit, SAM and .SYSTEM registry hives) from multiple Windows systems simultaneously. This customized version improves the original by accepting an input file with a list of target hosts and by supporting multithreading for faster operations. 

## Usage

The basic syntax to run the script is:

```shell
python3 secretsdump.py [domain/]username[:password] -t THREADS -inputfile INPUTFILE [options]
```

The main arguments are:

- `-t THREADS`, `-threads THREADS`: Number of concurrent threads. Replace THREADS with the desired number.
- `-inputfile INPUTFILE`: A text file with a list of target hosts, one per line. Replace INPUTFILE with the path to your file.
- `-outputfile OUTPUTFILE`: Path to the output directory if desired (optional). Will create dump files in this directory based on target, username, and domain (if specified). Replace OUTPUTFILE with the path to your directory.

The target argument follows this pattern: `[domain/]username[:password]`.

Refer to the script's inline help (-h, --help) for a description of all options.

## Example

Here's an example running the script with an input file (`hosts.txt`) and 5 concurrent threads:

```shell
python3 secretsdump.py mydomain/myuser:mypassword -t 5 -inputfile hosts.txt
```

This will start extracting secrets from all the hosts listed in `hosts.txt`, with 5 threads running simultaneously, and output the results to the current directory.

## Requirements

The script requires Python 3 and the `impacket` Python library, which you can install via pip:

```shell
pip3 install impacket
```

## Disclaimer

Use this tool responsibly. Do not use it for illegal activities. The author is not responsible for any misuse.