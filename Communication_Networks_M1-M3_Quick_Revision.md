# Communication Networks M1–M3 — Last-Minute Revision Sheet

## Must-practice diagrams

1. Data-communication components — Module 1 slide/PDF page 1.
2. Simplex, half-duplex and full-duplex — Module 1 page 3.
3. Mesh, star, bus and ring — Module 1 pages 6–7.
4. TCP/IP layers — Module 1 pages 17–20.
5. Encapsulation/decapsulation — Module 1 page 21.
6. OSI seven-layer model — Module 1 pages 23–25.
7. Character/bit framing and stuffing — Module 2 pages 6–7.
8. Simple and Stop-and-Wait protocol FSM/flow — Module 2 pages 8–15.
9. Pure and Slotted ALOHA vulnerable time — Module 2 pages 18–24.
10. CSMA/CD and CSMA/CA flowcharts — Module 2 pages 29–32.
11. Reservation, polling and token passing — Module 2 pages 33–36.
12. FDMA, TDMA and CDMA — Module 2 pages 37–41.
13. Ethernet frame format — Module 3 pages 3–4.
14. 10Base5/2/T/F implementations — Module 3 pages 6–8.

## Must-memorize formulas

- Full mesh links: `n(n−1)/2`; ports per device: `n−1`.
- Frame time: `T = frame size / channel rate`.
- Pure ALOHA: `S = G e^(−2G)`, maximum `18.4%` at `G = 0.5`, vulnerable time `2T`.
- Slotted ALOHA: `S = G e^(−G)`, maximum `36.8%` at `G = 1`, vulnerable time `T`.
- Ethernet propagation: `Tprop = distance / propagation speed`.
- Collision detection condition: `Ttx ≥ 2Tprop`.
- Approximate Ethernet efficiency used in the bank: `η ≈ 1/(1+2a)`, where `a=Tprop/Ttx`.

## Numerical final answers

### Pure ALOHA, 200-bit frames, 200 kbps

- 1000 frames/s → 135.3 successful frames/s = 27.1 kbps.
- 500 frames/s → 183.9 successful frames/s = 36.8 kbps.
- 250 frames/s → 151.6 successful frames/s = 30.3 kbps.

### Slotted ALOHA, same parameters

- 1000 frames/s → 367.9 successful frames/s = 73.6 kbps.
- 500 frames/s → 303.3 successful frames/s = 60.7 kbps.
- 250 frames/s → 194.7 successful frames/s = 38.9 kbps.

### Ethernet timing

- Q6: `Ttx=51.2 μs`, `Tprop=12.5 μs`, round trip `25 μs`, `a≈0.244`, collision detection possible, `η≈67.2%`.
- Q7 using the question-stated 12 Mbps: `Ttx≈42.67 μs`, `Tprop=5 μs`, round trip `10 μs`, `a≈0.117`, collision detection possible, `η≈81.0%`.

## MAC-address shortcut

Convert the first octet or inspect its second hexadecimal digit:

- I/G bit 0 (second hex digit even) → unicast.
- I/G bit 1 (second hex digit odd) → multicast.
- All `FF` → broadcast.

Verified examples: `4A` unicast, `47` multicast, `4B` multicast, `48` unicast.

## Highest-priority long answers

1. TCP/IP and OSI layers; OSI–TCP/IP comparison.
2. Encapsulation, addressing, multiplexing and demultiplexing.
3. Topologies and switching.
4. Framing, Stop-and-Wait ARQ, Pure/Slotted ALOHA.
5. CSMA persistence, CSMA/CD and CSMA/CA.
6. Controlled access and channelization.
7. Ethernet frame and Standard Ethernet implementations.
