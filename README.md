readme
1. Import necessary libraries: The code starts by importing required Python libraries, including `json` for data serialization, `hashlib` for SHA256 hashing, `logging` for logging messages, and the `qiskit` library for quantum computing.

2. Define the number of qubits: The variable `NUM_QUBITS` is set to 10, representing the number of qubits to be used for quantum communication.

3. Set up the logger: The logging configuration is set up to log informational messages during the execution of the protocol.

4. Define the quantum functions: Several functions are defined to create and manipulate quantum circuits. These functions include:
   - `create_entangled_qubits`: Creates an entangled quantum circuit with a specified number of qubits. The function uses the `QuantumCircuit` class from Qiskit to create the circuit.
   - `encode_owner_data`: Encodes the owner's data as qubits in the quantum circuit. It flips qubits to '1' depending on the data provided.
   - `entanglement_swapping`: Performs entanglement swapping between distant qubits. This is a crucial step for quantum repeaters, allowing long-distance quantum communication.
   - `quantum_repeater`: Implements quantum repeaters by repeatedly applying entanglement swapping to extend the communication distance.

5. Implement the BB84 protocol:
   - The `bb84_protocol` function implements the BB84 protocol for Quantum Key Distribution (QKD).
   - The owner's data (`owner_data`) is provided as a string, which will be encoded as qubits.
   - Random bases and bits are generated for Alice and random bases are generated for Bob.
   - The owner's data is encoded as qubits using the `encode_owner_data` function.
   - Qubits are transformed based on Alice's bases and bits using X and H gates.
   - Qubits are transformed based on Bob's bases using H gates.
   - Quantum repeaters are applied using the `quantum_repeater` function to extend the communication distance.
   - The qubits are measured at the end to obtain the measurement outcomes (counts) for each possible state.

6. Verify the shared key:
   - The `verify_shared_key` function is used to verify the shared key between Alice and Bob.
   - If Alice and Bob used the same basis for measurements, the function measures the first qubit to obtain the shared key.
   - The shared key is then compared with Alice's basis to check if the key is valid or if tampering has occurred.

7. Save results to a secure file:
   - After executing the BB84 protocol and verifying the shared key, the results are saved to a secure JSON file (`secure_results.json`).
   - The file contains the owner's data, owner's data hash, counts from the quantum measurement, and shared basis information.

By running the code, you would execute the BB84 protocol, which enables secure communication by generating shared keys between Alice and Bob using quantum properties. The secure JSON file `secure_results.json` will contain the necessary information for further communication between the two parties. Note that this code is intended for educational purposes and simulations using the Aer simulator. To implement it on a real quantum computer, you would need access to appropriate hardware.  please be aware this is not a currency it is not a crypto iit is a security protocol its does have a way gor future but this was not mentbfor that it is ment to to protect your assets dont code it into the smart contract only if you know what your doing
(stickman s, helped by chat gpt)

(elevator pitch) 

Imagine you have a magic box that can send secret messages using special particles called qubits. These qubits are like tiny balls that can spin in different ways, and they can be connected to each other in a special way called "entanglement."

So, here's how it works:

1. **Creating Entanglement**: You and your friend, let's call them Alice and Bob, want to talk secretly. First, you both create a bunch of these qubits and make them "entangled" by connecting them in a special pattern.

2. **Encoding Secrets**: Imagine you have a bunch of coins. If you want to send a secret message, you flip some of the coins to heads and some to tails. This is like how Alice puts her secret information into the qubits. If the qubit spins in a certain way, it means a "1," and if it spins another way, it means a "0."

3. **Mixing Things Up**: Alice and Bob have a special way to mix up these qubits' spins without revealing the secret. They use special actions to change how the qubits are spinning. This is like adding extra flips to the coins.

4. **Checking the Secrets**: Now, they both talk to each other and say how they made the qubits spin. They don't tell exactly what they did, just some hints. If they did the same thing, they know they can use those qubits to make a secret code. If they didn't do the same thing, they know someone tried to mess with the qubits.

5. **Sharing the Secret Code**: After they make sure everything is okay, they can use the qubits that match to make a secret code. They can use this code to send messages only they can understand.

So, the benefits are that Alice and Bob can send secret messages over long distances without worrying about someone listening in. This can be really useful for things like secure online banking, private conversations, or sharing confidential information.

However, there are things they need to be careful about:
- They must keep the qubits safe and not let anyone else touch them.
- They need to make sure nobody is trying to change the qubits while they're being sent.
- They should use this method only for things that need to be super secure, not for regular conversations.

Now, let's talk about smart contracts. A smart contract is like a digital agreement that automatically follows rules. It can't understand qubits directly, but people can use the information from qubits to create a secure agreement on the blockchain using a smart contract. This way, they can make sure that both sides follow the rules and keep things safe.
