This project implements a reliable data transfer (RDT) protocol, version 2.2, based on the Stop-and-Wait method. The protocol ensures that data is transmitted reliably over an unreliable network, where message corruption is possible, but packet loss and out-of-order delivery are not.

Key Features:
Message Integrity: The sender and receiver use checksums to detect corruption in transmitted packets, ensuring data integrity.
Stop-and-Wait Mechanism: The sender transmits a packet and waits for an acknowledgment from the receiver before sending the next one. This guarantees that no packet is lost or overlooked.
Retransmission on Corruption: If a corrupted packet or acknowledgment is detected, the sender retransmits the data until successful delivery is confirmed.
Sequence Numbers: A sequence number is used to differentiate between new and old packets, preventing duplicate data delivery in cases where acknowledgments are corrupted.
Receiver Feedback: The receiver validates incoming packets by checking for corruption and verifying the expected sequence number. It sends feedback to the sender indicating whether the packet was received correctly.
Project Flow:
Sender: The sender creates packets with data, sequence numbers, and checksums. It then transmits each packet and waits for feedback. If corruption is detected, the sender retransmits the packet.
Receiver: The receiver checks each packet for corruption and expected sequence numbers. If valid, it sends an acknowledgment to the sender and processes the data. If not, it requests a retransmission.

Collaborators: Youssef Elshamy, Salma Rashad, Nabila Sherif
