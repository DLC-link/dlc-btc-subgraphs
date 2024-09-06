# dlcBTC Arbitrum subgraph

## Start From This Repo

* Create a new subgraph fromhttps://thegraph.com/studio/

* Install Graph CLI with either npm or yarn

  * ```cmd
    npm install -g @graphprotocol/graph-cli
    ```

  * ```cmd
    yarn global add @graphprotocol/graph-cli
    ```

* clone this repo

* Authenticate in CLI, check your subgraph page.

* Deploy subgraph

  * ```cmd
    graph deploy --studio test
    ```





## Start From Zero

Since our token contract is a proxy contract, we need to create two subgraphs: the first subgraph should use the address of our proxy contract, and the second subgraph should use the address of our token implementation.

* Install Graph CLI with either npm or yarn

  * ```cmd
    npm install -g @graphprotocol/graph-cli
    ```

  * ```cmd
    yarn global add @graphprotocol/graph-cli
    ```

* Create first subgraph using proxy contract's address

  * ```
    graph init --studio your_first_subgraph_name
    ```

* Create second subgraph using address of token implementation

  * ```
    graph init --studio your_second_subgraph_name
    ```

* Merge the content of the following files from the second subgraph into the first subgraph files by copying and pasting.

  * Files under `abis` , `generated` , `src` , `tests`.
  * file `schema.graphql`
  * `entities` and `eventHandlers` in file `subgraph.yaml`

* Authenticate in CLI, check your subgraph page.

* ```
  cd your_first_subgraph_name
  ```

* Build subgraph

  * ```
    graph codegen && graph build
    ```

* Deploy subgraph

  * ```cmd
    graph deploy --studio test
    ```



