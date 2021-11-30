```
This article contains the introductory operations of Ethereum geth client, including command line creation of new private chain, account query, new account, inter account transfer, and a brief introduction to Ethereum account system.
```

## Introduction to Ethereum geth

After entering the geth command line mode, we can use the following command to create a new private chain:

```
geth --datadir "./" --nodiscover console 2>>geth.log
```

Enter command line mode, where parameters
-- dataDir represents the folder address,
-– nodiscover means that the chain does not want to be discovered by other nodes,
-Console > > geth.log means to output the console to the file geth.log
Of course, it is also very simple to exit from the command line mode. Just enter exit to exit

### 1、 Query account

Eth.accounts on the get command line
Enter eth.accounts on the command line to see the current blockchain in total and the public key address of each account.
View current Ethereum account

```
eth.accounts
```

By the way, Ethereum's account system:
In the Ethereum system, the state is composed of objects called "accounts" (each account consists of a 20 byte address) and state transitions that transfer value and information between two accounts. Ethereum's account consists of four parts:
-- random number, used to determine the counter that each transaction can only be processed once
-Current Ethernet balance of the account
-Contract code of the account, if any
-Account storage (empty by default)
Simply put, each Ethereum account consists of a pair of public and private keys.
The public key can be understood as the account address, which can be accessed by any other account. The private key can be understood as an encrypted password. This pair of public keys and private keys together form a unique Ethereum account.
For example, in the first Ethereum account eth. Accounts [0] we established in the previous section, the address

```
0xf283f210898597c15fd14181236e6fe53630b38c
```

It is the public key, and the private key is encrypted by the password.

### 2、 New account

*The string in parentheses is the password of the new account*

```
personal.newAccount（“123456”）
```

![img](https://img2018.cnblogs.com/blog/1486009/201902/1486009-20190219141651165-963000342.png)
At this point, enter eth. Accounts, and you can easily see the public key addresses of two accounts
![img](https://img2018.cnblogs.com/blog/1486009/201902/1486009-20190219141749120-233803349.png)
Let's look at the balance of two accounts
![img](https://img2018.cnblogs.com/blog/1486009/201902/1486009-20190219141814521-1839207836.png)

### 3、 Inter account transfer

At this time, we can use eth.sendtransaction to transfer 0.1 ethers from user1 to user2, which indicates that our account is locked, so we need to unlock the account.
![img](https://img2018.cnblogs.com/blog/1486009/201902/1486009-20190219141814521-1839207836.png)
After unlocking the account, the transfer operation is successful. The printed address is the address of this transaction. Check the balance of user2 account after Ethereum transfer again, but it is found that user2 account is still 0. This is because there are no miners to mine. According to the concept of blockchain, we know that each transaction confirmation actually needs mining, that is, it can be confirmed by consensus of other miners before it can be added to the account book of blockchain.
![img](https://img2018.cnblogs.com/blog/1486009/201902/1486009-20190219141856597-1190037004.png)
The above is the simplest entry operation of geth: account query, new account creation, transfer, and a simple introduction to Ethereum account system!
