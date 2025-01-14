import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs groupId="execution-clients" defaultValue="geth" values={[
{label: 'Nethermind', value: 'nethermind'},
{label: 'Besu', value: 'besu'},
{label: 'Geth', value: 'geth'}
]}>
  <TabItem value="nethermind">
   <p class='hidden-in-jwt-guide'>Download the latest stable release of Nethermind for your operating system from the <a href='https://downloads.nethermind.io/'>Nethermind downloads page</a>. Extract the contents into your <code>execution</code> folder. Run the following command to start your execution node:</p>
    <Tabs groupId="network" defaultValue="mainnet" values={[
        {label: 'Mainnet', value: 'mainnet'},
        {label: 'Goerli-Prater', value: 'goerli-prater'},
        {label: 'Sepolia', value: 'sepolia'},
        {label: 'Ropsten', value: 'ropsten'}
    ]}>
      <TabItem value="mainnet">
        <Tabs className='tabs-hidden-in-jwt-guide' groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>Nethermind.Runner --JsonRpc.Enabled true --HealthChecks.Enabled true --HealthChecks.UIEnabled true --JsonRpc.JwtSecretFile=../consensus/jwt.hex --JsonRpc.Host=0.0.0.0</code></pre></TabItem>
                <TabItem value="ipc"><div class="admonition admonition-info alert alert--info"><div class="admonition-content"><p>Content under construction.</p></div></div></TabItem>
            </Tabs>
      </TabItem>
      <TabItem value="goerli-prater">
          <Tabs className='tabs-hidden-in-jwt-guide' groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>Nethermind.Runner --config goerli --JsonRpc.Enabled true  --HealthChecks.Enabled true --HealthChecks.UIEnabled true --JsonRpc.JwtSecretFile=../consensus/jwt.hex --JsonRpc.Host=0.0.0.0</code></pre></TabItem>
                <TabItem value="ipc"><div class="admonition admonition-info alert alert--info"><div class="admonition-content"><p>Content under construction.</p></div></div></TabItem>
            </Tabs>
      </TabItem>
      <TabItem value="sepolia">
        <Tabs className='tabs-hidden-in-jwt-guide' groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>Nethermind.Runner --config sepolia --JsonRpc.Enabled true --HealthChecks.Enabled true --HealthChecks.UIEnabled true --JsonRpc.JwtSecretFile=../consensus/jwt.hex --JsonRpc.Host=0.0.0.0 --Merge.TerminalTotalDifficulty 17000000000000000</code></pre></TabItem>
                <TabItem value="ipc"><div class="admonition admonition-info alert alert--info"><div class="admonition-content"><p>Content under construction.</p></div></div></TabItem>
            </Tabs>
      </TabItem>
      <TabItem value="ropsten">
        <Tabs className='tabs-hidden-in-jwt-guide'  groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>Nethermind.Runner --config ropsten --JsonRpc.Enabled true --HealthChecks.Enabled true --HealthChecks.UIEnabled true --JsonRpc.JwtSecretFile=../consensus/jwt.hex --JsonRpc.Host=0.0.0.0 --Merge.TerminalTotalDifficulty 50000000000000000</code></pre></TabItem>
                <TabItem value="ipc"><div class="admonition admonition-info alert alert--info"><div class="admonition-content"><p>Content under construction.</p></div></div></TabItem>
            </Tabs>
      </TabItem>
    </Tabs>
    <p>See Nethermind's <a href='https://docs.nethermind.io/nethermind/ethereum-client/configuration'>command-line options</a> for parameter definitions.</p>
    <p class='hidden-in-jwt-guide'>Your Nethermind execution node will begin syncing. This can take a long time - from hours to days. You can <a href='https://docs.nethermind.io/nethermind/ethereum-client/monitoring-node-health'>check your Nethermind execution node's sync status</a> by navigating to <a href='http://localhost:8545/healthchecks-ui'><code>http://localhost:8545/healthchecks-ui</code></a> or by running the following command from a separate terminal window:</p>

```
curl localhost:8545/health 
```

  <p>A sync status of <code>false</code> indicates that your node is fully synced. You can proceed to the next step while Nethermind syncs.</p>
  </TabItem>
  <TabItem value="besu">
    <p class='hidden-in-jwt-guide'>Ensure that the latest 64-bit version of the <a href='https://www.oracle.com/java/technologies/downloads/'>Java JDK</a> is installed. Download the latest stable release of Besu from the <a href='https://github.com/hyperledger/besu/releases'>Besu releases</a> page. OS-specific instructions are available on Besu's <a href='https://besu.hyperledger.org/en/stable/HowTo/Get-Started/Installation-Options/Install-Binaries/'>binary installation page</a>. Run the following command to start your execution node:</p>
    <Tabs groupId="network" defaultValue="mainnet" values={[
        {label: 'Mainnet', value: 'mainnet'},
        {label: 'Goerli-Prater', value: 'goerli-prater'},
        {label: 'Sepolia', value: 'sepolia'},
        {label: 'Ropsten', value: 'ropsten'}
    ]}>
      <TabItem value="mainnet">
          <Tabs className='tabs-hidden-in-jwt-guide'  groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>besu --rpc-http-enabled --engine-jwt-enabled=true --engine-jwt-secret=path/to/jwt.hex  --engine-host-allowlist="*"</code></pre></TabItem>
                <TabItem value="ipc"><div class="admonition admonition-danger alert alert--info"><div class="admonition-content"><p>Content under construction.</p></div></div></TabItem>
            </Tabs>
      </TabItem>
      <TabItem value="goerli-prater">
        <Tabs className='tabs-hidden-in-jwt-guide'  groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>besu --network=goerli --rpc-http-enabled --engine-jwt-enabled=true --engine-jwt-secret=path/to/jwt.hex  --engine-host-allowlist="*"</code></pre></TabItem>
                <TabItem value="ipc"><div class="admonition admonition-danger alert alert--info"><div class="admonition-content"><p>Content under construction.</p></div></div></TabItem>
            </Tabs>
      </TabItem>
      <TabItem value="sepolia">
        <Tabs className='tabs-hidden-in-jwt-guide'  groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>besu --network=sepolia --rpc-http-enabled --engine-jwt-enabled=true --engine-jwt-secret=../consensus/jwt.hex --engine-host-allowlist="*" --override-genesis-config="terminalTotalDifficulty=17000000000000000"</code></pre></TabItem>
                <TabItem value="ipc"><div class="admonition admonition-danger alert alert--info"><div class="admonition-content"><p>Content under construction.</p></div></div></TabItem>
            </Tabs>
      </TabItem>
      <TabItem value="ropsten">
        <Tabs className='tabs-hidden-in-jwt-guide'  groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>besu --network=ropsten --rpc-http-enabled --engine-jwt-enabled=true --engine-jwt-secret=../consensus/jwt.hex --engine-host-allowlist="*" --override-genesis-config="terminalTotalDifficulty=50000000000000000"</code></pre></TabItem>
                <TabItem value="ipc"><div class="admonition admonition-danger alert alert--info"><div class="admonition-content"><p>Content under construction.</p></div></div></TabItem>
            </Tabs>
      </TabItem>
    </Tabs>
    <p>See Besu's <a href='https://besu.hyperledger.org/en/stable/Reference/CLI/CLI-Syntax/'>command-line options</a> for parameter definitions.</p>
    <p>Your Besu execution node will begin syncing. You can <a href='https://besu.hyperledger.org/en/stable/Reference/API-Methods/#eth_syncing'>check your Besu execution node's sync status</a> by running the following command from a separate terminal window:</p>

```
curl -H "Content-Type: application/json" -X POST http://localhost:8545 -d "{""jsonrpc"":""2.0"",""method"":""eth_syncing"",""params"":[],""id"":51}" 
```

  <p>A sync status of <code>false</code> indicates that your node is fully synced. You can proceed to the next step while Besu syncs.</p>
  </TabItem>
  <TabItem value="geth">
    <p class='hidden-in-jwt-guide'>Download and run the latest 64-bit stable release of the <strong>Geth installer</strong> for your operating system from the <a href='https://geth.ethereum.org/downloads/'>Geth downloads page</a>.</p>
    <div class="admonition admonition-danger alert alert--danger"><div class="admonition-content"><p>Note that Geth 1.10.22 contains a regression. Update to <a href='https://github.com/ethereum/go-ethereum/releases'>v1.10.23+</a> if you haven't already.</p></div></div>
    <p class='hidden-in-jwt-guide hidden-in-mergeprep-guide'>Navigate to your <code>execution</code> directory and run the following command to start your execution node:</p>
     <p class='hidden-in-jwt-guide hidden-in-quickstart'>Run the following command to start your execution node:</p>
    <Tabs groupId="network" defaultValue="mainnet" values={[
        {label: 'Mainnet', value: 'mainnet'},
        {label: 'Goerli-Prater', value: 'goerli-prater'},
        {label: 'Sepolia', value: 'sepolia'},
        {label: 'Ropsten', value: 'ropsten'}
    ]}>
      <TabItem value="mainnet">
        <Tabs className='tabs-hidden-in-jwt-guide'  groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>geth --http --http.api eth,net,engine,admin --datadir . --authrpc.jwtsecret ../consensus/jwt.hex </code></pre></TabItem>
                <TabItem value="ipc"><pre><code>geth --http --http.api eth,net,engine,admin --datadir . </code></pre></TabItem>
            </Tabs>
      </TabItem>
      <TabItem value="goerli-prater">
        <Tabs className='tabs-hidden-in-jwt-guide'  groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>geth --goerli --http --http.api eth,net,engine,admin --datadir . --authrpc.jwtsecret ../consensus/jwt.hex </code></pre></TabItem>
                <TabItem value="ipc"><pre><code>geth --goerli --http --http.api eth,net,engine,admin --datadir . </code></pre></TabItem>
            </Tabs>
      </TabItem>
      <TabItem value="sepolia">
        <Tabs className='tabs-hidden-in-jwt-guide'  groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>geth --sepolia --http --http.api eth,net,engine,admin --datadir . --authrpc.jwtsecret ../consensus/jwt.hex --override.terminaltotaldifficulty 17000000000000000</code></pre></TabItem>
                <TabItem value="ipc"><pre><code>geth --sepolia --http --http.api eth,net,engine,admin --datadir . --override.terminaltotaldifficulty 17000000000000000</code></pre></TabItem>
            </Tabs>
      </TabItem>
      <TabItem value="ropsten">
        <Tabs className='tabs-hidden-in-jwt-guide'  groupId="protocol" defaultValue="jwt" values={[
            {label: 'JWT', value: 'jwt'},
            {label: 'IPC', value: 'ipc'}
            ]}>
                <TabItem value="jwt"><pre><code>geth --ropsten --http --http.api eth,net,engine,admin --datadir . --authrpc.jwtsecret ../consensus/jwt.hex --override.terminaltotaldifficulty 50000000000000000</code></pre></TabItem>
                <TabItem value="ipc"><pre><code>geth --ropsten --http --http.api eth,net,engine,admin --datadir . </code></pre></TabItem>
            </Tabs>
      </TabItem>
    </Tabs>
    <p>See Geth's <a href='https://geth.ethereum.org/docs/interface/command-line-options'>command-line options</a> for parameter definitions.</p>
    <p>Your Geth execution node will begin syncing. You can check your Geth execution node's sync status by running the following commands from a separate terminal window:</p>

```
## if you're not using Windows
geth attach 

## if you're using Windows
geth attach ipc:\\.\pipe\geth.ipc
eth.syncing
```

  <p>A sync status of <code>false</code> indicates that your node is fully synced. You can proceed to the next step while Geth syncs.</p>
  </TabItem>
</Tabs>

