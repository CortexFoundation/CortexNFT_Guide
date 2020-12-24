# How to upload your own NFT to Cortex Blockchain
## Upload metadata to IPFS
follow the instruction (https://docs.ipfs.io/install/command-line/) to install **IPFS** on your machine.
Start your own IPFS node:
```
ipfs daemon
```
Open a new tab, goto the directory where the NFT image (*example.jpg*) is located, upload it to IPFS:
```
ipfs add example.jpg
```
Terminal will output something like: 
```
added QmcoxJV7ypCFDPhjiHUxeUw4g9Sy6uULiJKrgpFphh6jbG example.jpg
```
Create a metadata file (*metadata.json*) with the NFT's information and the image hash from last step (`QmcoxJV7ypCFDPhjiHUxeUw4g9Sy6uULiJKrgpFphh6jbG`):
```
{
    "title": "Asset Metadata",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "Demo NFT"
        },
        "description": {
            "type": "string",
            "description": "This NFT is created for demonstration"
        },
        "author" : {
            "type": "string",
            "description":"Cortex"
        },
        "image": {
            "type": "string",
            "description": "https://ipfs.io/ipfs/QmcoxJV7ypCFDPhjiHUxeUw4g9Sy6uULiJKrgpFphh6jbG"
        }
    }
}

```
Upload the metadata to IPFS:
```
ipfs add metadata.json
```
