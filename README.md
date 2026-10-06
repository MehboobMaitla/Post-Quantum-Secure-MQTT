# Comparative Security & Cryptographic Performance Study of MQTT over TLS 1.3

## 1. Overview
This repository evaluates traditional and post-quantum cryptographic performance characteristics when applied to secure MQTT communication pipelines over TLS 1.3 protocol standards.

## 2. Research Question
"How does the choice of cryptographic algorithm affect MQTT communication performance?"

## 3. Experiment
We measure the computational and network transaction overhead of traditional asymmetric algorithms (RSA-2048, ECC-P256) inside active TLS 1.3 handshake and transmission loops. Additionally, we conduct a distinct, standalone baseline benchmark of the post-quantum ML-KEM-768 primitive to analyze key exchange and encapsulation steps.

## 4. Results
Performance metrics tracked include connection establishment latency (ms), round-trip publication time (ms), CPU usage, memory utilization, and delivery success rate.

## 5. How to Run
Open the provided Google Colab notebook (`MQTT_TLS_Security_Study.ipynb`) and execute all cells sequentially from top to bottom. It will programmatically configure certificates, initiate the local broker, and run the benchmark loops.

## 6. Limitations
- The environment utilizes a clean local loopback interface (no artificial packet loss or cross-country WAN latency).
- Standard Python TLS implementation binds to standard system OpenSSL configurations; thus ML-KEM-768 is benchmarked as an isolated primitive.

## 7. Future Work
- Integrating and compiling OQS-Provider with OpenSSL 3.x to execute actual hybrid post-quantum TLS 1.3 handshakes.
- Implementing packet level delays using WAN simulation tooling.
