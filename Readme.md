# Platon



```
git clone -b release-0.11.0 https://github.com/PlatONnetwork/PlatON-Go.git --recursive
make all
sudo cp -f ./build/bin/platon /usr/bin/
sudo cp -f ./build/bin/keytool /usr/bin/
keytool genkeypair | tee >(grep "PrivateKey" | awk '{print $2}' > ./data/nodekey) >(grep "PublicKey" | awk '{print $3}' > ./data/nodeid)
mkdir -p ~/platon-node/data && keytool genblskeypair | tee >(grep "PrivateKey" | awk '{print $2}' > ./data/blskey) >(grep "PublicKey" | awk '{print $3}' > ./data/blspub)
nohup platon --identity platon --datadir ./data --port 16789 --testnet --rpcport 6789 --rpcapi "db,platon,net,web3,admin,personal" --rpc --nodekey ./data/nodekey --cbft.blskey ./data/blskey --verbosity 3 --rpcaddr 127.0.0.1 --syncmode "full" > ./data/platon.log 2>&1 &
platon attach http://localhost:6789
> admin.peers
> platon.blockNumber

```


:~/platon-node# platon attach http://localhost:6789
Welcome to the PlatON JavaScript console!

instance: PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.14
at block: 60298 (Mon, 31 Mar 52104 00:56:48 CST)
 datadir: /root/platon-node/data
 modules: admin:1.0 net:1.0 personal:1.0 platon:1.0 rpc:1.0 web3:1.0

> admin.peers
[{
    caps: ["cbft/1", "platon/63"],
    id: "0bec2b85c14eaba5adcc87b7d9119ec0902fbbe8f4dcf53d64479aee9f64fe05831e14286f8b4402b4b4d7291eaa41eff7ba2b98207fc55da59c081c7b5a94fd",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.13.1",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:52120",
      remoteAddress: "152.32.134.214:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5483975,
        highestQCBn: 5484306,
        lockedBn: 5483976,
        protocolVersion: 1
      },
      platon: {
        head: "0x7fcdeec4dcc695e1e88abddfd0a509d5d00b32639b94e1e2d80a004ea5631513",
        number: 5484289,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/62", "platon/63"],
    id: "0c0c0052ea92c26329f1ef24f64a83f6935aa524ebaaa5a3c8187cdc12cef115fa0d2dfa121079c8c085f808806a106c6b42d064f5bb593f508bdda49473c9a0",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.13.1",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:47290",
      remoteAddress: "47.92.247.171:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5483955,
        highestQCBn: 5483957,
        lockedBn: 5483956,
        protocolVersion: 1
      },
      platon: {
        head: "0x4c42697dd768bd7aaed0aba38cbcdc8fe3ee9e2f69600667525851b9b1870768",
        number: 5484311,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/62", "platon/63"],
    id: "225ca1243f98239f9748d7c34ed3482cdd2ff0570f6e40bb13523c1b489154c68b79731787b605f98d6debbf1766ab9fa919c56f5bd2e72d6c3ee6a41176372d",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.13.1",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:43018",
      remoteAddress: "152.32.253.35:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5484246,
        highestQCBn: 5484248,
        lockedBn: 5484247,
        protocolVersion: 1
      },
      platon: {
        head: "0x05d3963e0288cde6c78d335e5ddeaf12b566c7db149497caa7122bf764876aed",
        number: 5484304,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/62", "platon/63"],
    id: "3285db0b0c2d91377c27adc4ea08f1f6ee5af52bb00435e0d26da2379f60ad2e4026f3f77e0d3414622061b5da426856f55fe75387ca3b2fb8b97a2920f3f798",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.13.1",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:52986",
      remoteAddress: "120.132.116.194:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5483812,
        highestQCBn: 5483878,
        lockedBn: 5483813,
        protocolVersion: 1
      },
      platon: {
        head: "0xcdb801398a3453a8bfd1c4025992ff86540d252ed66259d9acbd86dc8db2fa2a",
        number: 5484316,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/62", "platon/63"],
    id: "3eb8c315e65abc22c3b89ddacd53c09ad82b1eb93310eefce0c8333c4c235c582307287a44776e3ac0bd38864cb1f201870d824112bb72ca8d9c7f3ae73fbba8",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.10.4",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:44402",
      remoteAddress: "150.158.109.143:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5484233,
        highestQCBn: 5484235,
        lockedBn: 5484234,
        protocolVersion: 1
      },
      platon: {
        head: "0x3399a3da69e3edf5e5b7a4882fad3c23f1804139823ff55635c1a13612b1cd69",
        number: 5484319,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/62", "platon/63"],
    id: "4ee863fab1a51f6e3d6cfac4721780ea37af037b1e695e0d100e74c4f4e3971db410a65e474f0148b7a424fbde38346df88d950d96fdbbc9c0a6abe222c34ae6",
    name: "PlatONnetwork/platon/v0.11.0-unstable/linux-amd64/go1.14",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:47148",
      remoteAddress: "132.232.50.132:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5483810,
        highestQCBn: 5483875,
        lockedBn: 5483811,
        protocolVersion: 1
      },
      platon: {
        head: "0x37a329eae0b17ad9c13b24c468ec266277794eea638f256f546ce07e30896e47",
        number: 5484312,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/62", "platon/63"],
    id: "54342caadd857ca1eceee27136540d9d5ccc380e76bc80e3c500089831ab06ddc477c449475896679aa96d11350b6aa8fc2ef536ea25aef422f06fcde52d90d2",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.13.1",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:50348",
      remoteAddress: "47.241.106.214:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5484051,
        highestQCBn: 5484307,
        lockedBn: 5484052,
        protocolVersion: 1
      },
      platon: {
        head: "0x6f09c86224a5da5666b3386ab445ceba606d70ba60465dfb3c8431985c878de2",
        number: 5484268,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/62", "platon/63"],
    id: "73601a21e758e4052b43e68d9c09f2750dbc82b1736cce6a52258d42a18cde6c006d1eae39d44dda08987362d0ba8f8df43df05b3330281e866207117de25885",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.13.1",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:35198",
      remoteAddress: "121.36.224.239:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5483975,
        highestQCBn: 5483977,
        lockedBn: 5483976,
        protocolVersion: 1
      },
      platon: {
        head: "0x5735878423f1fad6feaeaa9e1779e42ca218c395bbafbd44edf51ac5e4273aab",
        number: 5484314,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/63"],
    id: "78b35020f2b51862d9591404e1bacfd582bf8200ed5dfe80f19d9d9a23ea7cd04429719741e9f9d8e329d23da9414207e68bd82069dfecf37c700f22479087f7",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.13.1",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:53150",
      remoteAddress: "114.67.107.18:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5483912,
        highestQCBn: 5483914,
        lockedBn: 5483913,
        protocolVersion: 1
      },
      platon: {
        head: "0x59db39b3a45723e951d1e2d1562a78a8d846f0da9c6ab3aedb6704ede719a96e",
        number: 5484322,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/62", "platon/63"],
    id: "833961a5f492785bc0e43401658f1e908fe6581b66a0fc9175108074470dc229ec5a57059038b961bb81db72933948797b7b45f35fc96bf551f14ed0e1bd2973",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.14.2",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:41932",
      remoteAddress: "49.7.58.249:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5483813,
        highestQCBn: 5483879,
        lockedBn: 5483814,
        protocolVersion: 1
      },
      platon: {
        head: "0x2b2491d0146ccf034e7b8fc9d562adc8606cadbe6e523d2b9d3693052f2e7d11",
        number: 5484222,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/63"],
    id: "9648aa4879b5c7a1610ccc0a875491097d4d4d25fd18d78086ff006af88fcdf0bf5d17f7731a8d7e6fcd2236c86221143c64463791e2d07468a27d4f3dcf663d",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.13.1",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:35282",
      remoteAddress: "103.149.27.171:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5483798,
        highestQCBn: 5483877,
        lockedBn: 5483799,
        protocolVersion: 1
      },
      platon: {
        head: "0xd0eb8d5c466798dfeb765b9dbddcd4e3214799a7ad253c108dfc634a103ad293",
        number: 5484321,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/63"],
    id: "cc7511b6bb5ef017d39c7fa5b281335c0505ac4c1adc58479c00ac889516972445a289b4cd1c193770fb9c270f49373a22fd091f4d5ef669bb3f29e3a90d7cb6",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.14",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:43350",
      remoteAddress: "121.36.82.190:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5483886,
        highestQCBn: 5483888,
        lockedBn: 5483887,
        protocolVersion: 1
      },
      platon: {
        head: "0xcdb801398a3453a8bfd1c4025992ff86540d252ed66259d9acbd86dc8db2fa2a",
        number: 5484316,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/62", "platon/63"],
    id: "d0b692ce6232f291745e1a60c0ffd38e116bb7e8aa186bcd05513ea756e27080c5611174e4b51a2722c343fb2d495b24051997b297687673a5708562954546ce",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.13.1",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:54696",
      remoteAddress: "52.32.42.75:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5484254,
        highestQCBn: 5484256,
        lockedBn: 5484255,
        protocolVersion: 1
      },
      platon: {
        head: "0xd52e8d8aad0eb824b57ef1cc6d78e022058705c2664976c01fb9782b915ef061",
        number: 5484318,
        version: 63
      }
    }
}, {
    caps: ["cbft/1", "platon/62", "platon/63"],
    id: "dd6ee60b009eb680d8f5df8d919eeaf7e167b0ec435bdd5f9cf3a7c8c8ff50f77ac79faa005777dfbef50a66e9af31e0af39c3f3829880b26528f7c886b3cffc",
    name: "PlatONnetwork/platon/v0.11.0-unstable-03a3e7dc/linux-amd64/go1.13.1",
    network: {
      consensus: false,
      inbound: false,
      localAddress: "172.16.136.20:56296",
      remoteAddress: "152.32.254.108:16789",
      static: false,
      trusted: false
    },
    protocols: {
      cbft: {
        commitBn: 5483880,
        highestQCBn: 5483882,
        lockedBn: 5483881,
        protocolVersion: 1
      },
      platon: {
        head: "0x4c42697dd768bd7aaed0aba38cbcdc8fe3ee9e2f69600667525851b9b1870768",
        number: 5484311,
        version: 63
      }
    }
}]
> platon.blockNumber
63008



