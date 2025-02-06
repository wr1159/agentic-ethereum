<a href="https://decentralised-sam.vercel.app/">
  <h1 align="center">Decentralised S.A.M. (Species Assessment Mapper)</h1>
</a>

<p align="center">
Submission for Agentic Etheruem.
</p>

<p align="center">
A Decentralised AI Robotic Agent that maps out invasive species and uploads them to the blockchain to avoid censorship.
</p>

<p align="center">
  <a href="#todo"><strong>TODO</strong></a> ·
  <a href="#diagrams"><strong>Diagrams</strong></a> ·
  <a href="#clone-and-run-locally"><strong>Guide</strong></a> ·
</p>
<br/>

## TODO

### AI Agent (AgentKit)

-   [ ] Initialise Repo
-   [ ] Upload Image to IPFS
-   [ ] Create Tasks / Sightings for AVS (Upload location + IPFS Hash)

### AVS

-   [ ] Create Task / Sightings Structure
-   [ ] Create Task / Sightings Event Emitter
-   [ ] Create Operator Code on Task / Sightings(Run AI Modal)

### Frontend

-   [ ] View Sightings with Location and Image
-   [ ] Vote for whether it's correct

## Diagrams

```mermaid
graph LR;
    A[AI Agent] -->|Creates Task| B[AVS Contract on Base];
    B -->|Sends Image Data| C[Operator];
    D[Frontend] -->|User Interaction| B;
```

## Clone and run locally

### Contracts Instructions

1. Enter the contracts directory and start the local server with:

    ```bash
    anvil --chain-id 31337 --fork-url https://holesky.drpc.org
    ```

2. Run the deployment script with:

    ```bash
    forge script script/DeploySAMServiceManager.sol --rpc-url http://localhost:8545 --broadcast
    ```

3. Enter the operator directory under contracts and run the operator respondTask script

    ```bash
    bun run respondTask.ts
    ```

4. On a separate terminal, enter the operator directory under contracts and run the createTask script

    ```bash
      bun run createTask.ts
    ```

    You should see the `createTask` script create a `createTask` Transacton followed by the `respondTask` script create a `respondToTask` Transaction.

### Frontend Instructions

1. You can now run the Next.js local development server:

    ```bash
    npm run dev
    ```

    The starter kit should now be running on [localhost:3000](http://localhost:3000/).
