# Docker container for Ontology private-net

This is a pre-configured docker container setup in a multinode (4) configuration.  This was designed to allow developers to have a private Ontology blockchain that can be used for testing purposes.  This is an initial release and may contain limited functionality. Further updates will be made once a wallet is released.

Running Ontology node version 0.75
<br><br>
## Setup

#### Download Docker container
```
$ docker pull ontologycommunitydevelopers/ont-private:Multinode
```

#### Run container
```
$ docker run -itd -p 20334-20336:20334-20336 -p 21334-21336:21334-21336 -p 22334-22336:22334-22336 -p 23334-23336:23334-23336 ontologycommunitydevelopers/ont-private:Multinode
```

### Pre-configured nodes
Four nodes have been setup all with RPC, RESTful and WebSockets configured. See below table for details:

| Node | RESTful Port | WebSocket Port | RPC Port |
| --- | --- | --- | --- |
| 1 | 20334 | 20335 | 20336 |
| 2 | 21334 | 21335 | 21336 |
| 3 | 22334 | 22335 | 22336 |
| 4 | 23334 | 23335 | 23336 |


### Pre-configured node wallet addresses
| Node | Address | Password |
| --- | --- | --- |
| 1 | TA81GwHHpM1MEzfP35hfscdC5BxkUfFsbK | ont1 |
| 2 | TA7gqWVczawZhsCRUS6PYShP1jXkcT4uUX | ont2 |
| 3 | TA8mpRk8PiaKqBrRNgwSWeJ2DVrKECVcP9 | ont3 |
| 4 | TA9KDkvqcSUQcucWAkKTqQcekDLf7ecrAh | ont4 |

### Development address
An address has been setup for testing of functions that require ONT (transfers, invoking contracts, etc) - details are: <br>

Address: TA8HEr37yqME9RRrcCgTp9qZN2F1xdWPAz <br>
Private Key: c49921f30369a7047d4cfadfa7be7a3166fcc4e951ecb5913f87800bb22ba469 <br>
ONT Balance: 100,000,000

<br><br>
## Usage

### Example request
To get the current blockheight from Node 2 using a RESTful request:
```
Send a GET request to http://container-ip:21334/api/v1/block/height
```

Response:
```
{
    "Action": "getblockheight",
    "Desc": "SUCCESS",
    "Error": 0,
    "Result": 296,
    "Version": "1.0.0"
}
```

See https://github.com/ontio/documentation/blob/master/ontology-API/restfulapi.md for RESTful commands <br>
See https://github.com/ontio/documentation/blob/master/ontology-API/ontrpcapi.md for RPC commands <br>
(Websocket commands list coming soon)
