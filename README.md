# crypto-exchange
exchange
{
  "host": "https://nodes-testnet.wavesnodes.com",
  "chainId": "T", // W for mainnet and T for testnet
  
  // Address with a non-zero balance for deployment operations contracts
  "deposit": "seed phrase", 
  "contracts": [
    {
      // Required. path to local file
      "script": "path to contract file",

      // Optional. Use in other contracts like ENV vaariable ${MAIN_CONTRACT_ADDRESS}
      "anchor": "MAIN_CONTRACT_ADDRESS"

      // Optional. The amount that must be sent to the contract for it to work
      // 1400000 fee for contract deploy
      // >= 900000 per transaction
      "requestBalance": 10000000,

      // Optional. If it does not exist or is null, then create a new address for the contract
      "seed": "seed phrase",

      // Optional. Initializing contract after deploy 
      "init": {
        "addMember": [{
          "type": "string", // 'binary' | 'integer' | 'boolean' | 'string'
          "value": "...." // string | LONG | boolean
        }]
      }
    },
    // ...
    {
      "script": "path to contract file"
    }
  ]
}
