# 私钥获取
为方便获取，在 sk.txt 中放入的私钥，然后代码自动从中读取

# ERC20 合约部署
通过 deploy.js 进行部署，样例中链接的测试网为 Kovan, 对应需要使用有 Ether 的账户进行发送


# 发交易方式
 1 拼装交易
 ```
const tx = newbac.methods.send("0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266",100000, "fee").encodeABI();

   // Sign Tx with PK
   const createTransaction1 = await web3.eth.accounts.signTransaction(
       {
          to: createReceipt.contractAddress,
          data: tx,
          gas: 8000000,
       },
       account_from.privateKey
   );

   // Send Tx and Wait for Receipt
   const createReceipt1 = await web3.eth.sendSignedTransaction(
       createTransaction1.rawTransaction
   );
```
  
2 合约接口调用
  todo
  
  
  3 mocha测试框架：
  http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html
  https://pcaaron.github.io/pages/fe/block/improve4.html#%E8%B7%91%E6%B5%8B%E8%AF%95
  
  4 注意:
  Infura has not activated the method eth_sendTransaction because this method needs unlocked accounts on the ethereum node. With the example I've provided above will it also work with infura :)
  
  https://ethereum.stackexchange.com/questions/70853/the-method-eth-sendtransaction-does-not-exist-is-not-available-on-infura  