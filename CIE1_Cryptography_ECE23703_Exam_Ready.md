# ECE23703 Cryptography - CIE 1 Exam-Ready Master Guide

> **Course authority:** Global Academy of Technology autonomous course plan and teacher question bank.  
> **Exam:** CIE 1 - 8 September 2026 | **Pattern:** L3/application-focused | **Coverage:** Module 1 + Module 2 + half of Module 3.  
> **Likely half-Module 3 cutoff:** public-key principles and RSA are the high-confidence CIE core because they occur first in the local teaching sequence and are the only Module 3 topics in the teacher question bank. Diffie-Hellman, ElGamal and ECC are official ECE23703 Module 3 topics, but are labelled **Insurance for CIE 1** until the faculty confirms where “half Module 3” ends.  
> **Accuracy rule:** The two Hill-key images and AES AddRoundKey matrices in the legacy question-bank document are too low-resolution to transcribe without risk. Their methods are included, but exact answers remain prominently blocked rather than guessed.

## Start here — fastest routes

- **First study pass:** [Module 1](#cryptography--module-1-draft) → [Module 2](#module-2--block-ciphers-des-and-aes) → [Module 3 core](#part-a--core-answers-for-every-teacher-bank-question).
- **Last 24 hours:** priority sequence at [Emergency sequence](#5-emergency-sequence), then the [filled mock CIE](#8-ece23703-local-scope-mock-cie), then [rapid revision](#part-c--rapid-revision-sheet).
- **Find a teacher-bank answer:** use the [question-bank coverage index](#9-complete-teacher-question-bank-coverage-index).
- **Blocked image questions:** [Hill cipher](#4-hill-cipher--method-but-supplied-keys-are-unresolved) and [AES AddRoundKey numerical](#addroundkey-numerical-method-source-matrices-unresolved).
- **New-bank-only questions:** [Revised Question Bank Addendum](#revised-question-bank-addendum---new-module-1-3-questions).

## One-day crash route — follow this exactly

> **Goal:** maximize CIE marks, not master all five modules. Ignore revised-bank Modules 4–5 today unless the faculty explicitly changed the announced CIE scope.

| Time | Work | Required output |
|---|---|---|
| **0:00–0:20** | Read this route, priority rules, and the coverage index | Know what you will skip |
| **0:20–1:35** | Caesar, Playfair, rail fence, columnar transposition | Reproduce rules and four checked ciphertext/plaintext answers |
| **1:35–2:35** | Euclidean algorithm, EEA, modular arithmetic | Solve both old GCDs plus new EEA `(1759,550)` without notes |
| **2:35–2:50** | Break | No phone-based topic browsing |
| **2:50–4:10** | Block/stream, confusion/diffusion, Feistel and DES | Draw Feistel and DES structures twice from memory |
| **4:10–5:20** | AES State and four transformations, round flow, key expansion | Draw AES flow; practise the new MixColumns column |
| **5:20–5:40** | Break/food | Reset |
| **5:40–7:05** | Public-key principles and RSA | Solve all three RSA numericals and learn the attack list |
| **7:05–7:50** | Diffie–Hellman + MITM | Solve both new DH numericals and draw the sequence diagram |
| **7:50–8:20** | Insurance: ElGamal and ECC-DH | Learn only algorithm steps and diagrams |
| **8:20–9:20** | Attempt the 30-mark mock closed-book | Mark it immediately |
| **Final 40 min** | Repair mistakes; formula and diagram recall | No new chapters |

**If only four hours remain:** Playfair/EEA (50 min) → Feistel/DES/AES diagrams (75 min) → RSA numericals/theory (75 min) → DH numericals/MITM (30 min) → recall (10 min).  
**If only two hours remain:** memorise the symmetric model, one Playfair example, EEA steps, Feistel equations, AES round order, RSA chain and three RSA results. Treat DH as the first insurance topic.

---
# ECE23703 Cryptography Study Resources — Non-Module Sections

> **Local authority — read first.** This guide is planned from the Global Academy of Technology autonomous **ECE23703** course plan and teacher question bank. The local course is 4 credits with a 3:1:0 pattern; CIE 1 is on 8 September 2026, is L3/application-oriented, and covers Module 1, Module 2, and half of Module 3. External VTU course codes are enrichment only because their module ordering differs.

## 1. Authoritative planning facts and priority system

### Facts used here

- **Local course:** ECE23703 Cryptography, Global Academy of Technology, autonomous institution affiliated to VTU.
- **CIE 1:** 8 September 2026; 30 marks; Module 1 + Module 2 + half Module 3; L3 emphasis.
- **Local Module 1:** classical substitution/transposition ciphers, Euclidean algorithm, modular arithmetic, groups, rings and fields.
- **Local Module 2:** block/stream ciphers, Feistel/DES, and AES structure, transformations and key expansion.
- **Local Module 3:** public-key principles, RSA, Diffie-Hellman, ElGamal and elliptic-curve arithmetic. The likely CIE half-module cutoff is public-key principles + RSA, but this is an evidence-based inference rather than a faculty-confirmed boundary.
- External BCS703/18CS744/21IS71 material is used only by matching topic names; its exam pattern is not used as the ECE23703 CIE pattern.

### Priority labels

Use these labels after intersecting the official/local syllabus with the CIE announcement.

| Priority | Meaning | Action |
|---|---|---|
| **P0 — must secure** | Explicitly in local CIE scope and repeated in lecturer material/QB | Learn definition, diagram, algorithm, one worked example, and an exam-ready answer. |
| **P1 — high return** | Explicit syllabus topic, likely long-answer/numerical, or repeated across credible QBs | Prepare a complete L3 answer and solve at least one numerical or comparison. |
| **P2 — supporting** | Required prerequisite, short-answer item, or connective concept | Make a compact definition/formula/diagram card. |
| **P3 — verify before spending time** | Found in another scheme, unofficial notes, or an unverified web source only | Do not treat as local scope until confirmed. |

A practical tie-breaker is **local evidence first, official syllabus second, affiliated-college material third, web summaries last**. A topic appearing only in a search result is not evidence that it will be examined.

## 2. L3 answer template

Use **L3 (long-answer level)** for a 10/20-mark response. Adjust length to the marks and local CIE format.

1. **State the objective and definition.** Give the security goal or mathematical problem in 2–4 precise lines.
2. **Draw the system/flow diagram.** Label sender, receiver, key(s), attacker, message/ciphertext, and verification/decryption path where relevant.
3. **State notation and assumptions.** Define symbols such as `p`, `q`, `n`, `e`, `d`, `g`, `x`, `h`, block size, or key space before using them.
4. **Give the algorithm in numbered steps.** Separate setup/key generation, operation, and recovery/verification.
5. **Work a small example.** Show intermediate modular arithmetic or a short transformation; do not jump from input to final answer.
6. **Explain correctness/security intuition.** State why the receiver can recover/verify and what assumption or attack model matters.
7. **Add a comparison or limitation.** For example: symmetric vs asymmetric, DES vs AES if locally included, DH vs RSA, hash vs encryption, or MITM vulnerability.
8. **Close with an application and one caution.** Keep the conclusion tied to the question.

**Presentation check:** headings, numbered steps, readable equations, a labelled diagram, units/bit lengths where applicable, and a final boxed result. Never substitute a memorised paragraph for the requested derivation.

## 3. Beginner smart-work method

### The 4-pass loop

- **Pass 1 — map (20–30 min):** Copy the local CIE scope into a three-column table: topic, expected answer type, evidence source. Mark P0–P3.
- **Pass 2 — understand (one focused block):** Read one primary note or lecture section. Write a six-line explanation from memory. For algorithms, write inputs, steps, outputs, and one toy example.
- **Pass 3 — retrieve (closed book):** Attempt a question-bank question or blank-page reconstruction. Mark every missing step, symbol, diagram, and condition.
- **Pass 4 — compress (10 min):** Convert the correction into a revision card. Reattempt after a gap, rather than rereading immediately.

### Smart constraints for a beginner

- Use **one main source per topic**, not five parallel playlists.
- Watch only enough video to remove a specific confusion; pause and solve before continuing.
- For every algorithm, maintain one canonical worked example and one “failure/attack/limitation” note.
- Spend roughly **60% on active writing and solving, 25% on understanding, 15% on organising**.
- If a topic is outside the local announced scope, label it **parking lot** instead of letting it displace P0/P1 work.
- End every study block with a 3-minute oral recall: “What is it? How does it work? What can fail?”

## 4. Realistic timetable backward from 8 September 2026

This is a compressed plan for a student starting on **31 August 2026**. Shift the first day if necessary, but preserve the order and the final timed practice.

| Date | Main objective | Output before stopping |
|---|---|---|
| **Mon 31 Aug** | Confirm ECE23703 syllabus/CIE scope; build topic inventory; classify P0–P3 | One-page scope map and question-bank coverage sheet |
| **Tue 1 Sep** | M1 foundations and classical-cipher items that are locally included | Two L3 skeletons, one worked numerical, one comparison card |
| **Wed 2 Sep** | M1 number theory: Euclidean algorithm, modular arithmetic, EEA, group/ring/field | Formula sheet, both GCDs, EEA check, and two theory answers |
| **Thu 3 Sep** | M2 block/stream, confusion/diffusion, Feistel and DES | Feistel equations plus two labelled structures from memory |
| **Fri 4 Sep** | M2 AES State, transformations, encryption/decryption and key expansion | AES flow, transformation table, and diagram rehearsal |
| **Sat 5 Sep** | M3 public-key principles and complete RSA preparation | Secrecy/authentication diagrams, RSA sheet, and verified numerical |
| **Sun 6 Sep** | Mixed retrieval and first local-scope mock CIE | Marked mock, error log, and three weakest topics |
| **Mon 7 Sep** | Repair weakest topics; rewrite only failed answers; light recall at night | Final two-page revision pack and exam logistics check |
| **Tue 8 Sep** | Exam day: 30–45 min recall only; no new topic | Definitions, formulas, diagrams, and answer-order plan |

**Daily minimum:** two 75–90-minute deep-work blocks plus one 30-minute retrieval block. If time is lost, preserve the order **scope verification → P0/P1 algorithms/numericals → timed writing → revision**, and drop P3 browsing first.

## 5. Emergency sequence

If less than 24 hours remains:

1. Obtain the lecturer’s exact ECE23703 CIE scope and remove all unconfirmed topics.
2. Select **one dependable answer route per local module**: definition/diagram, algorithm, worked example, limitation/application.
3. Memorise the notation and prerequisites needed to start each numerical.
4. Write one 20-mark answer per module under time pressure; correct it immediately using the rubric below.
5. Build a final sheet containing only formulas, key-generation steps, attack names, diagrams, and comparison points.
6. Sleep enough to write clearly. Do not spend the final hour discovering new playlists or unofficial “important questions.”

If less than three hours remains: scope check (15 min), formula/diagram recall (35 min), three answer skeletons (60 min), error correction (30 min), logistics and calm review (20 min).

## 6. Revision sheets and checklists

### One-page topic card

- Topic and local module: ____________________
- Priority/evidence: ____________________
- Security objective: ____________________
- Inputs, outputs, and notation: ____________________
- Five algorithm steps: ____________________
- Worked example/result: ____________________
- Diagram to draw: ____________________
- Attack/limitation: ____________________
- Comparison/application: ____________________
- One likely question: ____________________

### Numerical checklist

- [ ] Copied all given values and the required output.
- [ ] Defined modulus, exponents, keys, and intermediate variables.
- [ ] Reduced intermediate values modulo the correct number.
- [ ] Checked gcd/invertibility conditions where required.
- [ ] Shown enough working for method marks.
- [ ] Performed a reverse/check operation where possible.
- [ ] Boxed the final answer and stated its interpretation.

### L3 writing checklist

- [ ] Directly answered the verb: explain, derive, compare, compute, or justify.
- [ ] Included a labelled diagram or flow where useful.
- [ ] Numbered the algorithm rather than writing an unstructured paragraph.
- [ ] Explained the security assumption and at least one limitation.
- [ ] Used consistent symbols and did not omit key-generation conditions.
- [ ] Left time to scan for sign, modulo, and notation errors.

## 7. Common mistakes

- Mixing **ECE23703 scope** with BCS703, 18CS744/18EC744, 21IS71, or older 15CS61 content without checking the local syllabus.
- Treating a question-bank frequency as a prediction or guarantee.
- Writing RSA/DH steps without distinguishing public values, private values, and the shared/derived result.
- Forgetting gcd, primality, invertibility, or parameter conditions in modular algorithms.
- Calling a hash “encryption” or implying that hashing is reversible.
- Describing DH as automatically authenticated and omitting the MITM issue.
- Giving a cipher name without a security model, key space, or attack limitation.
- Copying a diagram with unlabeled arrows and no indication of who owns each key.
- Watching a long lecture passively instead of closing it and reproducing the algorithm.
- Using an unofficial module number as proof of local ordering.
- Inventing or copying an unverified YouTube video ID, playlist ID, paper year, or question wording.

## 8. ECE23703 local-scope mock CIE

> This is a **30-mark practice paper** built from the local course plan and teacher question bank. It is not a prediction of the actual paper.

**Suggested time: 60 minutes. Attempt all questions.**

### Q1 — Module 1 application (10 marks)

1. Explain the Caesar-cipher algorithm. Encrypt `WORK IS WORSHIP` using key `k=3`. Show the reverse check. **(6)**
2. Use the Euclidean algorithm to find `gcd(1970,1066)`. **(4)**

**Answer checkpoints:** `ZRUN LV ZRUVKLS`; `gcd=2`.

### Q2 — Module 2 structure (10 marks)

Draw and explain one Feistel round using the correct equations. Then explain why Feistel decryption uses the same structure with round keys in reverse order. Add four DES design facts: block size, effective key size, number of rounds, and round-function input/output sizes.

**Answer checkpoints:** `L_i=R_(i-1)` and `R_i=L_(i-1) XOR F(R_(i-1),K_i)`; DES uses a 64-bit block, 56-bit effective key, 16 rounds, and `F:32 bits + 48-bit subkey -> 32 bits`.

### Q3 — Module 3 core application (10 marks)

For RSA, use `p=17`, `q=11`, `e=7`, and message `M=88`.

1. Generate the public and private keys. **(5)**
2. Encrypt and decrypt the message, showing modular arithmetic and the round-trip check. **(5)**

**Answer checkpoints:** `n=187`, `phi(n)=160`, `d=23`, `C=11`, recovered plaintext `88`.

### Self-scoring rubric

| Criterion | Marks per 10-mark answer |
|---|---:|
| Correct definition/notation/given data | 1 |
| Correct labelled diagram or algorithm | 3 |
| Complete working/application | 4 |
| Verification, limitation, or conclusion | 1 |
| Clear presentation and boxed result | 1 |

**Score interpretation:** 25–30 = exam ready; 20–24 = revise mistakes only; 15–19 = rewrite weakest answer closed-book; below 15 = return to the P0 sequence.

## 9. Complete teacher question-bank coverage index

All substantive local teacher-bank prompts are mapped below. Repeated prompts point to one canonical answer.

| Module | Teacher-bank cluster | Canonical guide section | Status |
|---|---|---|---|
| M1 | Simplified/model of symmetric encryption | Module 1 §1 | Complete |
| M1 | Caesar encrypt/decrypt numericals | Module 1 §2.1 | Complete and reverse-checked |
| M1 | Playfair encrypt/decrypt numericals | Module 1 §3 | Complete and reverse-checked |
| M1 | Hill encrypt `SECURITY`; decrypt `PQCFKU` | Module 1 §4 | **Blocked: exact image keys unreadable** |
| M1 | Transposition concept/example | Module 1 §5 opening worked example | Complete |
| M1 | Rail fence and columnar transposition | Module 1 §5 numericals | Complete; assumptions stated |
| M1 | Euclidean algorithm and both GCDs | Module 1 §6 | Complete and checked |
| M1 | Modular properties/proofs and `117 mod 13` | Module 1 §7 | Complete; wording issue noted |
| M1 | EEA `(161,28)` and coefficients | Module 1 §8 | Complete: `gcd=7, x=-1, y=6` |
| M1 | Group, ring and field | Module 1 §9 | Complete |
| M2 | Block/stream; substitution/permutation; diffusion/confusion | Module 2 §§1–2 | Complete |
| M2 | Feistel encryption/decryption/design | Module 2 §3 | Complete |
| M2 | DES overall structure/decryption | Module 2 §4 | Complete |
| M2 | AES overall structure, State, transforms, round, key expansion, `g`, S/IS-box | Module 2 §§5–10 | Complete |
| M2 | AES AddRoundKey state/key numerical | Module 2 AddRoundKey subsection | **Blocked: exact image matrices unreadable** |
| M3 | Key roles and asymmetric terminology/PKI | Module 3 Q1–Q2 | Complete |
| M3 | Secure public-key requirements and six ingredients | Module 3 Q3–Q4 | Complete |
| M3 | Public/private-key models; conventional comparison | Module 3 Q5–Q6 | Complete |
| M3 | Secrecy and authentication models | Module 3 Q7–Q8 | Complete |
| M3 | RSA algorithm and local numerical | Module 3 Q9–Q10 | Complete and independently checked |

**Ready rule:** “Complete” means the guide contains a checked answer. You become personally ready only after reproducing it closed-book once after a delay.

## 10. Previous-paper and web-evidence warnings

- The research ledger identifies a **VTUSync important-question resource** and an **SVIT BCS703 question bank** dated 06 Oct 2025. The available compact summary did not expose a complete internally consistent question count, so this guide makes no exact count claim. These are practice leads, not proof of ECE23703 CIE questions or predictions.
- VTUSync and SVIT materials have stronger provenance than generic search pages, but neither replaces the local lecturer’s scope.
- The 18CS744 PYQ listing records sessions Mar 2022, Aug 2022, Feb 2023, Jul 2023, and Jan 2024, but the ledger says the landing pages did not expose verified question text/direct PDFs. Do not quote or reconstruct questions from the listing.
- SearchCreators is reported as paywalled/inaccessible for verification. Do not infer paper content from its claims.
- 21CS733 and 21IS71 were identified as possible scheme/branch alternatives, but detailed verification was unavailable in the ledger. Treat them as leads only.
- Module ordering differs across BCS703, 18CS744/18EC744, 21IS71-like, and older 15CS61 materials. Match **topic names**, not module numbers.
- A previous paper shows what was asked once; it does not establish repetition, marks, current scheme, or local CIE scope. Preserve the original source, date, page, and institution for every claim.

## 11. Video-resource ledger and safe links

**Link rule:** The ledger supplied four exact Module III video IDs. They are reproduced as direct links below. For topics without an exact verified URL in the ledger, only transparent YouTube search URLs are provided; these are labelled **search link**, not a specific video or playlist. No playlist IDs are inferred.

### Exact direct video URLs present in the ledger

- VTU e-Shikshana Module III Session 1 — [direct video](https://www.youtube.com/watch?v=BQ4VowkFDK8) — 30:17.
- VTU e-Shikshana Module III Session 2 — [direct video](https://www.youtube.com/watch?v=cbJcAgfaSg0) — 51:00.
- VTU e-Shikshana Module III Session 3 — [direct video](https://www.youtube.com/watch?v=FZ-PJWvGCUQ) — 43:41.
- VTU e-Shikshana Module III Session 4 — [direct video](https://www.youtube.com/watch?v=U8YyGMS7bag) — 46:08.

### Verified search links where no exact topic URL was supplied

Use the local topic list to select a result; verify the title, channel, and syllabus match before studying.

- [Search link — BCS703 Module 1](https://www.youtube.com/results?search_query=BCS703+cryptography+module+1)
- [Search link — BCS703 Module 2](https://www.youtube.com/results?search_query=BCS703+cryptography+module+2)
- [Search link — BCS703 Module 3](https://www.youtube.com/results?search_query=BCS703+cryptography+module+3)
- [Search link — VTU cryptography module 1](https://www.youtube.com/results?search_query=VTU+cryptography+module+1)
- [Search link — RSA and Diffie-Hellman VTU](https://www.youtube.com/results?search_query=VTU+RSA+Diffie+Hellman+cryptography)
- [Search link — DES and AES VTU](https://www.youtube.com/results?search_query=VTU+DES+AES+cryptography)
- [Search link — Euclidean and extended Euclidean algorithm](https://www.youtube.com/results?search_query=Euclidean+extended+Euclidean+algorithm+cryptography)
- [Search link — hash functions and PKI VTU](https://www.youtube.com/results?search_query=VTU+hash+functions+PKI+X.509+cryptography)

The video ledger reports strong concise backup channels including Neso Academy, Gate Smashers, 5 Minutes Engineering, Trouble-Free, VTU padhai, and VTU e-Shikshana. Channel presence is not a guarantee that a particular result follows ECE23703; check the topic and solve from the local syllabus.

## 12. Source ledger for syllabus and study leads

- Official VTU scheme/syllabus landing page: <https://vtu.ac.in/en/b-e-scheme-syllabus/>
- Official 2022 CSE Semester 7 syllabus PDF: <https://vtu.ac.in/pdf/2022_3to8/7csesyll.pdf>
- VTUSync important QB download: <https://drive.google.com/uc?export=download&id=1sxCYZ29fJbC13D68tNTkgpJXxw276BUy>
- SVIT BCS703 QB download: <https://drive.google.com/uc?export=download&id=1Xt6XObmeXK1SenXvebhOW1O09IP2fU0S>
- SVIT BCS703 notes landing page: <https://vtusync.in/cryptography-network-security-bcs703-notes-6-svit/>
- East Point BCS703 notes landing page: <https://vtusync.in/cryptography-network-security-bcs703-notes-1-east-point/>
- 18CS744 syllabus mirror: <https://www.vturesource.com/vtu-syllabus/cs/2018/7/18CS744>
- 18CS744 PYQ listing: <https://www.vturesource.com/vtu-question-papers/CS/2018/18CS744/Cryptography>

**Final guardrail:** Before using any item in an answer, write its local-scope status in the coverage index. If the status is “verify,” ask the lecturer/class group or compare the official local syllabus; do not upgrade it to “confirmed” because a web page calls it important.

---

# Cryptography — Module 1 Draft

**Scope.** Classical encryption techniques; basic number theory and finite fields. Conventions follow Stallings and the local Module 1 slides. Unless stated otherwise, use `A=0, B=1, ..., Z=25`, arithmetic modulo 26, and omit spaces while processing cipher letters.

## 1. Basic vocabulary and symmetric encryption

- **Plaintext (P or X):** the original readable message.
- **Encryption/enciphering:** a reversible transformation of plaintext into ciphertext.
- **Ciphertext (C or Y):** the scrambled, unreadable output.
- **Secret key (K):** the value controlling the exact substitutions/permutations. Sender and receiver share it.
- **Decryption/deciphering:** the inverse transformation recovering plaintext.
- **Cryptography:** designing ciphers; **cryptanalysis:** attempting to recover plaintext or key without the secret; **cryptology:** both.

### Simplified symmetric-encryption model

```text
                 shared secret key K
                 /                  \
Plaintext X --> [ Encryption E ] --> Ciphertext Y
                                      |
                                      v  transmitted over insecure channel
                 shared secret key K  |
Ciphertext Y -> [ Decryption D ] ----+--> Plaintext X

                 Y = E(K, X),       X = D(K, Y)
```

Exam-ready answer: a symmetric system has five ingredients—plaintext, encryption algorithm, secret key, ciphertext, and decryption algorithm. The algorithm may be public; the key must remain secret. Security requires a strong algorithm and secure key distribution/storage. The receiver uses the same key to invert the encryption.

### Model of a symmetric cryptosystem

```text
 Message source                         Destination
      | X                                     ^ X
      v                                       |
 [Encryption E] -- Y = E(K,X) --> [Decryption D]
      ^                              ^
      | K                            | K
   Key source ---- secure channel ---+

 Cryptanalyst observes Y and knows E,D; it tries to estimate X or K.
```

For a message `X = [X1,...,XM]` and key `K`, encryption gives `Y = E(K,X)` and decryption gives `X = D(K,Y)`. The opponent is normally assumed to know the algorithms (Kerckhoffs-style assumption) but not K.

### Three useful classifications

1. **Operation:** substitution (replace symbols) and transposition (rearrange symbols); practical ciphers often combine both.
2. **Keys:** same key = symmetric; different keys = asymmetric.
3. **Processing:** block cipher processes fixed-size blocks; stream cipher processes continuously, one element at a time.

A brute-force attack tries keys until recognizable plaintext appears; on average about half the keyspace is tested. Cryptanalysis uses structure, statistics, or known plaintext/ciphertext relationships.

## 2. Substitution techniques

A substitution cipher replaces each plaintext symbol or group by another symbol/group. A transposition cipher leaves symbols unchanged but changes their order.

### 2.1 Caesar cipher

For plaintext letter value `p` and key/shift `k`:

```text
Encryption: C = E(k,p) = (p + k) mod 26
Decryption: P = D(k,C) = (C - k) mod 26
```

The classical Caesar cipher uses `k=3`; a general Caesar cipher permits `k=1,...,25`. The alphabet wraps around, so after Z comes A. It is weak because only 25 nontrivial keys exist.

#### Numerical: encrypt `WORK IS WORSHIP`

Use `k=3`, preserve spaces only for presentation:

```text
W O R K   I S   W O R S H I P
Z R U N   L V   Z R U V K L S
```

**Ciphertext:** `ZRUN LV ZRUVKLS`.

Independent reverse check: subtract 3:
`ZRUNLVZRUVKLS -> WORKISWORSHIP`.

#### Numerical: ciphertext `ZSNAJWXNYDGJQLFZR`, determine the key

Try Caesar shifts (or recognize the English candidate). With decryption shift `k=5`:

```text
Z S N A J W X N Y D G J Q L F Z R
U N I V E R S I T Y B E L G A U M
```

Therefore **key = 5** and **plaintext = `UNIVERSITY BELGAUM`**.

Independent reverse check: encrypt `UNIVERSITYBELGAUM` with `C=(P+5) mod 26` to obtain `ZSNAJWXNYDGJQLFZR`.

## 3. Playfair cipher

Playfair encrypts plaintext **digraphs** rather than single letters. Construct a 5x5 square from the keyword, remove repeated letters, merge I/J, then append unused alphabet letters.

Rules for preparing plaintext:

1. Split into pairs.
2. If a pair has repeated letters, insert filler X between them (`BALLOON -> BA LX LO ON`).
3. If one letter remains, append X.
4. Treat J as I under the I/J convention.

Rules for a pair:

- Same row: replace each letter by the letter immediately to its right, wrapping around.
- Same column: replace each by the letter immediately below, wrapping around.
- Rectangle: replace each by the letter in its own row and the other letter's column.

### Numerical: key `ENCRYPT`, encrypt `MATCH FIXED`

Remove duplicate key letters and merge I/J. Square:

```text
E N C R Y
P T A B D
F G H I K
L M O Q S
U V W X Z
```

Prepared pairs:

```text
MA  TC  HF  IX  ED
```

Transformations:

```text
MA -> OT   (same row, move right)
TC -> AN   (rectangle)
HF -> IG   (same row, move right)
IX -> QE   (same column, move down with wrapping)
ED -> YP   (rectangle)
```

**Ciphertext:** `OTANIGQEYP`.

Independent reverse check: decrypt `OT AN IG QE YP`; it returns `MA TC HF IX ED`, i.e. `MATCHFIXED`. No filler was inserted—the `X` is an actual letter in `FIXED`.

### Numerical: key `MINIMUM`, decrypt `IMWNIAUP`

Square:

```text
M I N U A
B C D E F
G H K L O
P Q R S T
V W X Y Z
```

Ciphertext pairs and reverse transformations:

```text
IM -> MA   (same row, move left with wrapping)
WN -> XI   (rectangle)
IA -> MU   (same row, move left)
UP -> MS   (rectangle)
```

Raw decrypted pairs: `MA XI MU MS`.

**Plaintext:** `MAXIMUMS`.

Independent reverse check: encrypt `MA XI MU MS` to recover `IM WN IA UP`. The `X` is a genuine letter in `MAXIMUMS`, not a filler.

## 4. Hill cipher — method, but supplied keys are unresolved

**EXACT-KEY-UNRESOLVED (do not guess).** The question bank shows image placeholders (`[pic]`) instead of the matrices for both Hill questions. Therefore no unique numerical ciphertext/plaintext answer can be certified.

Use the following complete method once the exact key is supplied.

1. Map letters with `A=0,...,Z=25`.
2. Choose the stated block size `m`; split plaintext/ciphertext into blocks of m symbols and pad only if the instructor's convention says so.
3. With the local slide's column-vector convention, write `P` as an m-by-1 vector and compute
   `C = K P (mod 26)`.
   (Stallings' text uses row vectors and writes `C = P K`; do not mix conventions.)
4. For decryption, calculate `det(K)`. An inverse exists modulo 26 only if `gcd(det(K),26)=1`.
5. Compute `K^-1 = det(K)^-1 adj(K) (mod 26)` and then
   `P = K^-1 C (mod 26)` for column vectors.
6. Reverse-check every block by recomputing the opposite transformation.

For the question **“Encrypt SECURITY using Hill Cipher. Key [pic]”**: exact key unresolved; result intentionally withheld.

For **“Decrypt PQCFKU using Hill Cipher. Key [pic]”**: exact key unresolved; result intentionally withheld.

**Malformed/modular wording note.** The source material alternates between row-vector (`C=PK`) and column-vector (`C=KP`) notation and contains image-only key placeholders. The matrix orientation and exact matrix must be confirmed before calculating.

## 5. Transposition techniques

Transposition rearranges plaintext positions without changing the symbols. Example: write in rows and read columns.

```text
Plaintext:  MEETMEAFTERTHETOGAPARTY
Rows:       M E E T M E
            A F T E R T
            H E T O G A
            P A R T Y X
Read columns (one possible convention): M A H P / E F E A / E T T R / T E O T / M R G Y / E T A X
```

The key specifies the column readout order. Different padding and spacing conventions can produce different final strings, so state them.

### Rail-fence cipher: `HAPPY BIRTHDAY TO YOU`

The question omits the rail count. **Assumption: standard 3-rail zigzag, spaces removed, no padding.**

```text
Rail 1: H . . Y . . O
Rail 2: . A . P B R H A T Y U
Rail 3: . . P . . I . . D . O
```

Reading rails gives:

**Ciphertext (3 rails): `HYTYOAPBRHATYUPIDO`.**

Independent reverse check: write this ciphertext back along a 3-rail zigzag and read diagonally to obtain `HAPPYBIRTHDAYTOYOU`.

If a different rail count is intended, the answer changes; for reference, 2 rails gives `HPYITDYOAPBRHATYU`.

### Columnar transposition: `COME HOME TOMORROW`, key `456123`

Spaces removed: `COMEHOMETOMORROW`. Write six columns under the six-digit key, left to right:

```text
Key:  4 5 6 1 2 3
      C O M E H O
      M E T O M O
      R R O W
```

Read columns in increasing key order `1,2,3,4,5,6`, retaining only occupied cells:

```text
1 -> E O W
2 -> H M
3 -> O O
4 -> C M R
5 -> O E R
6 -> M T O
```

**Ciphertext:** `EOWHMOOCMROERMTO`.

Independent reverse check: place the six output column strings back under key digits 1 through 6, restore columns to physical order 4,5,6,1,2,3, then read rows to recover `COMEHOMETOMORROW`.

## 6. Euclidean algorithm and GCD

The Euclidean algorithm repeatedly uses

```text
gcd(a,b) = gcd(b, a mod b),     gcd(a,0)=|a|.
```

It terminates when the remainder is zero; the last nonzero remainder is the GCD. It is efficient for large integers and is the basis of the extended Euclidean algorithm and modular inverses.

### `gcd(4655,12075)`

```text
12075 = 2(4655) + 2765
 4655 = 1(2765) + 1890
 2765 = 1(1890) + 875
 1890 = 2(875)  + 140
  875 = 6(140)  + 35
  140 = 4(35)   + 0
```

**GCD = 35.** Reverse check: 35 divides both 4655 (`35*133`) and 12075 (`35*345`), and the Euclidean chain proves no larger common divisor exists.

### `gcd(1970,1066)`

```text
1970 = 1(1066) + 904
1066 = 1(904)  + 162
 904 = 5(162)  + 94
 162 = 1(94)   + 68
  94 = 1(68)   + 26
  68 = 2(26)   + 16
  26 = 1(16)   + 10
  16 = 1(10)   + 6
  10 = 1(6)    + 4
   6 = 1(4)    + 2
   4 = 2(2)    + 0
```

**GCD = 2.** Reverse check: both inputs are even; dividing by 2 gives 985 and 533, which are coprime by the chain.

## 7. Modular arithmetic

`a mod n` is the nonnegative remainder when a is divided by positive n. Congruence means `a ≡ b (mod n)` exactly when `n | (a-b)`.

### Three operation properties (with proof idea)

If `a ≡ b (mod n)` and `c ≡ d (mod n)`, then:

1. **Addition:** `a+c ≡ b+d (mod n)`, because `(a+c)-(b+d)=(a-b)+(c-d)` is divisible by n.
2. **Subtraction:** `a-c ≡ b-d (mod n)`, because `(a-c)-(b-d)=(a-b)-(c-d)` is divisible by n.
3. **Multiplication:** `ac ≡ bd (mod n)`, since `ac-bd=a(c-d)+d(a-b)` is divisible by n.

A common computational form is to reduce operands first:
`[(a mod n)+(b mod n)] mod n = (a+b) mod n`, and similarly for subtraction and multiplication.

### Required checks

The question's expressions are correct, although the first line is written informally as `10 mod 8=2`:

```text
[(11 mod 8)+(15 mod 8)] mod 8 = (3+7) mod 8 = 10 mod 8 = 2
[(11 mod 8)-(15 mod 8)] mod 8 = (3-7) mod 8 = -4 mod 8 = 4
[(11 mod 8)*(15 mod 8)] mod 8 = (3*7) mod 8 = 21 mod 8 = 5
117 mod 13 = 0       (because 117 = 13*9)
```

**Malformed/modular wording note.** Negative remainders are convention-dependent in informal notation; here `-4 mod 8` means the least nonnegative residue 4. Also, “prove the three different properties” and “five different properties” refer to overlapping standard laws; state the exact laws being used.

### Five standard properties in `Z_n`

For all residues `a,b,c` in `Z_n`:

1. `(a+b) mod n = [(a mod n)+(b mod n)] mod n`.
2. `(a-b) mod n = [(a mod n)-(b mod n)] mod n`.
3. `(ab) mod n = [(a mod n)(b mod n)] mod n`.
4. Addition is associative and commutative, with identity 0 and additive inverse `-a mod n`.
5. Multiplication is associative and distributive over addition; multiplication is commutative in `Z_n`, with identity 1. A multiplicative inverse of a exists iff `gcd(a,n)=1`.

## 8. Extended Euclidean algorithm (EEA): `(161,28)`

Ordinary Euclid:

```text
161 = 5(28) + 21
 28 = 1(21) + 7
 21 = 3(7)  + 0
```

Thus `gcd(161,28)=7`. Back-substitute:

```text
7 = 28 - 21
  = 28 - (161 - 5*28)
  = -161 + 6*28
```

Therefore the Bézout coefficients are **x = -1, y = 6** in
`161x + 28y = gcd(161,28)`.

Independent reverse check:
`161(-1)+28(6) = -161+168 = 7`.

EEA is also used to find a modular inverse. Such an inverse exists only when the GCD is 1; here 161 and 28 are not relatively prime, so neither has an inverse of the other modulo the relevant modulus merely from this computation.

## 9. Group, ring, and field

These are algebraic structures: sets equipped with operations satisfying specified axioms.

### Group

A set `G` with one binary operation `*` is a group if it has:

1. **Closure:** `a*b` is in G.
2. **Associativity:** `(a*b)*c = a*(b*c)`.
3. **Identity:** an element e with `a*e=e*a=a`.
4. **Inverse:** each a has `a^-1` with `a*a^-1=a^-1*a=e`.

If additionally `a*b=b*a`, it is an **abelian group**. Example: integers under addition.

### Ring

A ring `R` has two operations, addition and multiplication. Under addition it is an abelian group; multiplication is closed and associative; multiplication distributes over addition:

```text
a(b+c)=ab+ac,       (a+b)c=ac+bc.
```

Some texts require a multiplicative identity 1 in a ring; state the convention. A commutative ring has `ab=ba`. An integral domain is a commutative ring with identity and no zero divisors.

### Field

A field is a commutative ring with identity in which every nonzero element has a multiplicative inverse. Thus addition, subtraction, multiplication, and division by a nonzero element stay within the set. Examples: rational, real, and complex numbers; `Z_p` is a field when p is prime. The integers are not a field because most integers have no integer multiplicative inverse.

## 10. Compact verification ledger

| Item | Convention/result | Independent check |
|---|---|---|
| Caesar `WORK IS WORSHIP` | `k=3` -> `ZRUN LV ZRUVKLS` | subtract 3 recovers plaintext |
| Caesar `ZSNAJWXNYDGJQLFZR` | `k=5`, `UNIVERSITY BELGAUM` | encrypt plaintext +5 recovers ciphertext |
| Playfair `ENCRYPT`, `MATCH FIXED` | square shown; `OTANIGQEYP` | decrypt gives `MA TC HF IX ED`; no filler used |
| Playfair `MINIMUM`, `IMWNIAUP` | pairs `MA XI MU MS` -> `MAXIMUMS` | re-encryption gives `IM WN IA UP`; X is genuine |
| Hill | exact key unresolved; no guessed answer | image placeholders prevent unique check |
| Rail fence | assumed 3 rails: `HYTYOAPBRHATYUPIDO` | zigzag reconstruction recovers message |
| Columnar `456123` | `EOWHMOOCMROERMTO` | inverse column placement recovers plaintext |
| GCD `(4655,12075)` | 35 | 35 divides both; Euclid ends at 35 |
| GCD `(1970,1066)` | 2 | Euclid ends at 2 |
| Modular examples | 2, 4, 5, and `117 mod 13=0` | direct remainder calculations |
| EEA `(161,28)` | gcd 7; `(x,y)=(-1,6)` | `161(-1)+28(6)=7` |
| Structures | group/ring/field definitions | axioms and examples stated |

---

# Module 2 — Block Ciphers, DES and AES

## How to use this draft

- **Beginner answer** gives the idea in plain language.
- **Exam-ready answer** gives definitions, equations, ordering and diagrams that can be reproduced in ASCII.
- Byte strings are written in hexadecimal with braces, for example `{53}`. AES matrices are written **by columns**: the first four input bytes fill column 0, the next four fill column 1, and so on.

---

## 1. Block cipher and stream cipher

### Beginner answer

A **stream cipher** encrypts data continuously, one bit or one byte at a time, by combining plaintext with a generated keystream. A **block cipher** collects a fixed-size block of plaintext, such as 64 or 128 bits, and transforms the complete block into a ciphertext block of the same size.

### Exam-ready answer

A stream cipher uses

```text
p0 p1 p2 p3 ...
 |  |  |  |
 k0 k1 k2 k3 ...       keystream
 |  |  |  |
XOR XOR XOR XOR
 |  |  |  |
c0 c1 c2 c3 ...
```

For bitwise XOR:

```text
c_i = p_i XOR k_i
p_i = c_i XOR k_i
```

A block cipher uses a keyed, reversible transformation:

```text
plaintext block P (n bits) --[ E_K ]--> ciphertext block C (n bits)
                                      |
                                      v
ciphertext block C (n bits) --[ D_K ]--> plaintext block P (n bits)
```

| Feature | Stream cipher | Block cipher |
|---|---|---|
| Unit of operation | Bit or byte | Fixed-size block |
| Main mechanism | Plaintext combined with keystream | Reversible keyed block transformation |
| Padding | Usually unnecessary | Often needed for the final partial block, depending on mode |
| Error behavior | Often localized to a bit/byte, depending on design | Depends strongly on the mode of operation |
| Typical sizes/examples | Vernam cipher, autokeyed Vigenere | DES: 64-bit block; AES: 128-bit block |
| Important requirement | Keystream must be unpredictable and never improperly reused | Permutation must be nonsingular/reversible |

An ideal one-time-pad stream cipher is secure when the keystream is truly random, as long as the plaintext, secret and never reused. Practical stream ciphers therefore need a cryptographically strong key-controlled bit-stream generator.

---

## 2. Substitution, permutation, confusion and diffusion

### Substitution

**Beginner:** Replace each symbol or group of symbols by another symbol or group, according to a key-controlled rule.

**Exam-ready:** A substitution maps an input element to a corresponding output element. In a reversible cipher, the mapping must be one-to-one. AES `SubBytes` is a byte substitution; a Feistel round also applies substitution through its round function.

```text
input element  --->  [ keyed substitution table/function ]  --->  output element
```

### Permutation

**Beginner:** Rearrange the positions without adding, deleting or changing the elements.

**Exam-ready:** A permutation changes only the order of a sequence. DES initial permutation and AES `ShiftRows` are examples of position rearrangement; AES `MixColumns` is a linear mixing operation rather than a pure permutation.

```text
[a b c d e f] ---> [c f a e d b]
```

### Diffusion

**Beginner:** Spread the influence of one plaintext bit over many ciphertext bits so that plaintext patterns and frequency statistics disappear.

**Exam-ready:** Diffusion makes the statistical relationship between plaintext and ciphertext complex. It is obtained by spreading each input bit/byte across many output positions. Repeated permutations and mixing operations provide diffusion. AES obtains strong diffusion from `ShiftRows` followed by `MixColumns`.

### Confusion

**Beginner:** Hide the relationship between the secret key and the ciphertext.

**Exam-ready:** Confusion makes the relationship between ciphertext statistics and the key value as complicated as possible. Complex nonlinear substitution, such as AES `SubBytes`, supplies confusion. Shannon's product-cipher idea alternates confusion and diffusion to resist statistical and algebraic attacks.

---

## 3. Feistel cipher structure

### Beginner answer

A Feistel cipher splits a block into a left half and a right half. Each round applies a function to the right half, combines it with the left half using XOR, and swaps the halves. The structure is reversible even when the round function itself is not reversible.

### General diagram

```text
                 round key K_i
                      |
L_(i-1) --------------|---------- XOR --------> R_i
                      |             ^
R_(i-1) ----> [ F(R_(i-1), K_i) ] ---+

R_(i-1) --------------------------------------> L_i

Round output:  L_i || R_i
```

For a 2w-bit block:

```text
input:  L_0 || R_0
                 |
              round 1
                 |
              round 2
                 |
                ...
                 |
              round n
                 |
output: R_n || L_n       (final swap convention)
```

### Encryption equations

The standard round equations are

```text
L_i = R_(i-1)
R_i = L_(i-1) XOR F(R_(i-1), K_i)
```

where `L_i` and `R_i` are w-bit halves and `K_i` is the subkey for round i.

If the implementation does not show a final swap separately, state its convention explicitly. In the common DES-style convention, after round n the transmitted preoutput is `R_n || L_n`.

### Why decryption works

From the encryption equations:

```text
R_(i-1) = L_i
L_(i-1) = R_i XOR F(L_i, K_i)
```

Thus the previous pair can be recovered using the same round structure and the subkeys in reverse order. No inverse of `F` is required.

### Feistel decryption algorithm

Given ciphertext `C = R_n || L_n` under the final-swap convention:

1. Split the ciphertext into the corresponding two halves.
2. Apply the same Feistel round computation.
3. Use `K_n, K_(n-1), ..., K_1` instead of `K_1, K_2, ..., K_n`.
4. Undo the final swap according to the stated convention.

```text
ciphertext
    |
    v
same Feistel network, but keys: K_n, K_(n-1), ..., K_1
    |
    v
plaintext
```

### Feistel parameters and design features

1. **Block size:** Larger blocks generally improve diffusion and reduce the value of simple statistical attacks, but may reduce speed and require more memory. Traditional designs commonly used 64 bits; AES uses 128 bits.
2. **Key size:** Larger keys improve brute-force resistance and generally improve confusion, but key setup may cost more. DES has an effective 56-bit key; AES supports 128-, 192- and 256-bit keys.
3. **Number of rounds:** One round is inadequate. More rounds increase security until the cost becomes excessive. DES uses 16 rounds.
4. **Subkey-generation algorithm:** It should produce sufficiently different, well-spread round keys and resist related-key and cryptanalytic attacks.
5. **Round function F:** It should provide nonlinear confusion, good diffusion, avalanche behavior and resistance to known attacks.
6. **Speed:** Software and hardware implementations should be efficient.
7. **Ease of analysis:** A clearly specified design is easier to test and obtain assurance about.

---

## 4. DES structure

### Beginner answer

DES encrypts a 64-bit data block using a 56-bit effective key. It first permutes the input, performs 16 Feistel rounds, swaps the halves, and applies the inverse permutation. The key is processed to generate 16 round subkeys.

### Exam-ready structure

```text
64-bit plaintext
       |
       v
Initial Permutation IP
       |
       v
L_0 || R_0       (32 bits || 32 bits)
       |
       v
+-------------------------------+
| Round 1: K_1                  |
| Round 2: K_2                  |
| ...                           |
| Round 16: K_16                |
| L_i = R_(i-1)                 |
| R_i = L_(i-1) XOR F(R_(i-1),K_i)|
+-------------------------------+
       |
       v
R_16 || L_16       (swap)
       |
       v
Inverse initial permutation IP^-1
       |
       v
64-bit ciphertext
```

DES round function `F` (right half 32 bits, subkey 48 bits):

```text
R_(i-1) (32)
     |
     v
Expansion E: 32 -> 48
     |
     XOR K_i (48)
     |
     v
Eight S-boxes: 48 -> 32
     |
     v
Permutation P
     |
     v
F(R_(i-1), K_i) (32)
```

DES key schedule:

```text
64-bit supplied key (8 parity bits)
              |
              v
PC-1: discard parity and permute -> 56 bits
              |
              v
C_0 || D_0 (28 || 28)
              |
       left circular shifts each round
              |
              v
PC-2 -> K_1, K_2, ..., K_16 (48 bits each)
```

### DES decryption

DES decryption uses the same Feistel structure. The initial permutation `IP` remains at the input and the inverse permutation `IP^-1` remains at the output; the only algorithmic change is that the round keys are applied in reverse order:

```text
K_16, K_15, ..., K_1
```

DES was standardized by NBS/NIST in 1977 as FIPS PUB 46. It operates on 64-bit blocks and has a 56-bit effective key. Its small key size makes exhaustive search feasible with modern resources, so AES replaced it for general-purpose protection.

---

## 5. AES overview and the State array

### Beginner answer

AES is a symmetric block cipher with a 128-bit block. The 16 input bytes are copied into a 4 x 4 byte matrix called the **State**. AES repeatedly transforms this State using substitution, row shifting, column mixing and round-key XOR.

### State layout

The bytes are loaded **column by column**:

```text
input bytes:  b0  b1  b2  b3  b4  b5  b6  b7  b8  b9  b10 b11 b12 b13 b14 b15

State =  [ b0   b4   b8   b12 ]
         [ b1   b5   b9   b13 ]
         [ b2   b6   b10  b14 ]
         [ b3   b7   b11  b15 ]
```

The State is a working 4 x 4 array of bytes. It is modified after each transformation and finally copied to the ciphertext output. The expanded key is also arranged as four-byte columns/words.

### AES variants

| Key length | Number of rounds | Expanded words |
|---:|---:|---:|
| 128 bits | 10 | 44 words |
| 192 bits | 12 | 52 words |
| 256 bits | 14 | 60 words |

All variants use a 128-bit block.

---

## 6. AES encryption and decryption — exact ordering

### Encryption ordering

For AES-128, encryption is:

```text
Input 128-bit block
        |
        v
Load State
        |
        v
AddRoundKey using round key K_0
        |
        v
Rounds 1 through 9:
    SubBytes -> ShiftRows -> MixColumns -> AddRoundKey(K_r)
        |
        v
Round 10 (final round):
    SubBytes -> ShiftRows -> AddRoundKey(K_10)
        |
        v
Ciphertext
```

**Important:** `MixColumns` is omitted in the final encryption round.

### Decryption ordering

The inverse operations are applied in reverse order. For AES-128:

```text
Ciphertext
        |
        v
AddRoundKey using K_10
        |
        v
Rounds 9 down to 1:
    InvShiftRows -> InvSubBytes -> AddRoundKey(K_r) -> InvMixColumns
        |
        v
Final inverse round:
    InvShiftRows -> InvSubBytes -> AddRoundKey(K_0)
        |
        v
Plaintext
```

`InvShiftRows` and `InvSubBytes` commute because they act on different byte attributes/positions, but the exam-safe standard listing is the one above. `InvMixColumns` is omitted from the final inverse round.

---

## 7. AES transformations

### 7.1 SubBytes

**Beginner:** Replace every State byte independently using the AES 16 x 16 S-box.

**Exam-ready:** For byte `{xy}`, use the high nibble `x` as the row and low nibble `y` as the column of the S-box. For example, the lecture notes give `{95} -> {2A}`. The S-box is a permutation of all 256 byte values and is constructed from a multiplicative inverse in `GF(2^8)` followed by an affine transformation.

```text
State byte {xy}
       |
       v
row = high nibble x; column = low nibble y
       |
       v
AES S-box lookup
       |
       v
substituted byte
```

### 7.2 ShiftRows

Rows are shifted cyclically to the left:

```text
Before:  [ a0  a1  a2  a3 ]
         [ b0  b1  b2  b3 ]
         [ c0  c1  c2  c3 ]
         [ d0  d1  d2  d3 ]

After:   [ a0  a1  a2  a3 ]       row 0: shift 0
         [ b1  b2  b3  b0 ]       row 1: shift 1 left
         [ c2  c3  c0  c1 ]       row 2: shift 2 left
         [ d3  d0  d1  d2 ]       row 3: shift 3 left
```

Because AES is stored by columns, this moves bytes between columns and contributes to diffusion. `InvShiftRows` performs the corresponding right circular shifts.

### 7.3 MixColumns

Each State column is treated as a four-byte vector and multiplied over `GF(2^8)` by the fixed matrix:

```text
[ s'0 ]   [02 03 01 01] [s0]
[ s'1 ] = [01 02 03 01] [s1]
[ s'2 ]   [01 01 02 03] [s2]
[ s'3 ]   [03 01 01 02] [s3]
```

For one column:

```text
s'0 = (02*s0) XOR (03*s1) XOR s2 XOR s3
s'1 = s0 XOR (02*s1) XOR (03*s2) XOR s3
s'2 = s0 XOR s1 XOR (02*s2) XOR (03*s3)
 s'3 = (03*s0) XOR s1 XOR s2 XOR (02*s3)
```

Multiplication is not ordinary integer multiplication; it is multiplication in `GF(2^8)` modulo the AES irreducible polynomial `x^8 + x^4 + x^3 + x + 1` (hexadecimal polynomial `0x11B`). `InvMixColumns` uses the inverse matrix:

```text
[0E 0B 0D 09]
[09 0E 0B 0D]
[0D 09 0E 0B]
[0B 0D 09 0E]
```

### 7.4 AddRoundKey

**Beginner:** XOR every State byte with the corresponding byte of the round key.

**Exam-ready:** The State and the 128-bit round key are aligned in the same column-major 4 x 4 layout. The operation is bytewise XOR:

```text
State' [r][c] = State[r][c] XOR RoundKey[r][c]
```

It is its own inverse:

```text
(A XOR K) XOR K = A
```

Therefore decryption uses AddRoundKey with the appropriate round key in reverse round order.

#### Numerical method

For each position, convert both entries to 8-bit binary, XOR corresponding bits, and convert back to hexadecimal.

Example for one byte:

```text
State byte     = {53} = 0101 0011
Round-key byte = {CA} = 1100 1010
XOR            =       1001 1001 = {99}
```

For a complete matrix, calculate independently at all 16 positions:

```text
[ a00 a01 a02 a03 ] XOR [ k00 k01 k02 k03 ]
[ a10 a11 a12 a13 ]     [ k10 k11 k12 k13 ]
[ a20 a21 a22 a23 ]     [ k20 k21 k22 k23 ]
[ a30 a31 a32 a33 ]     [ k30 k31 k32 k33 ]

= [a00 XOR k00, ... , a03 XOR k03]
  [a10 XOR k10, ... , a13 XOR k13]
  [a20 XOR k20, ... , a23 XOR k23]
  [a30 XOR k30, ... , a33 XOR k33]
```

> **EXACT-MATRICES-UNRESOLVED — DO NOT GUESS THE 16-BYTE STATE, THE 16-BYTE ROUND KEY, OR THE 16-BYTE RESULT.**
>
> The local question bank contains image placeholders (`[pic]`) rather than the numerical State and Round Key matrices. Only the XOR procedure and any individually supplied byte calculation can be verified from the available text. Insert the exact matrices before claiming a complete numerical result.

---

## 8. Inputs for a single AES round

A normal AES round receives the State after the previous round's AddRoundKey and a round key:

```text
State_(r-1)
     |
     v
 SubBytes -> ShiftRows -> MixColumns -> AddRoundKey with K_r -> State_r
```

Equivalently:

```text
T = MixColumns(ShiftRows(SubBytes(State_(r-1))))
State_r = T XOR K_r
```

For the final round:

```text
State_9 --SubBytes--> --ShiftRows--> T --XOR K_10--> Ciphertext
```

There is no `MixColumns` in the final round.

---

## 9. AES key expansion

### Beginner answer

AES expands the original key into enough round-key words for every round. For AES-128, the 16-byte key becomes 44 words, each word being 4 bytes. The first four words are the original key; later words depend on the word four positions earlier and on the previous word.

### Exam-ready algorithm

Let the key words be `w[0], w[1], ...`. For AES-128:

```text
w[0], w[1], w[2], w[3] = original 128-bit key

for i = 4 to 43:
    temp = w[i-1]
    if i mod 4 == 0:
        temp = g(temp) XOR Rcon[i/4]
    w[i] = w[i-4] XOR temp
```

The four words of round key `K_r` are:

```text
K_r = w[4r] || w[4r+1] || w[4r+2] || w[4r+3]
```

A reproducible AES-128 key-schedule diagram is:

```text
w0   w1   w2   w3          original key
 |    |    |    |
 +----+----+----+----> K0

w4 = w0 XOR g(w3) XOR Rcon1
w5 = w1 XOR w4
w6 = w2 XOR w5
w7 = w3 XOR w6                       -> K1

w8  = w4 XOR g(w7) XOR Rcon2
w9  = w5 XOR w8
w10 = w6 XOR w9
w11 = w7 XOR w10                      -> K2
```

For AES-192 and AES-256 the same principle is extended to 52 and 60 words respectively, with the additional AES-256 transformation applied when the word index satisfies the AES-256 schedule rule.

### The `g` function

For a 4-byte word `w = [a0 a1 a2 a3]`:

```text
RotWord:  [a0 a1 a2 a3] -> [a1 a2 a3 a0]
SubWord:  apply AES S-box to each byte
Rcon:     XOR the first byte with the round constant; other bytes are 00
```

Therefore:

```text
g([a0 a1 a2 a3]) = SubWord(RotWord([a0 a1 a2 a3])) XOR [Rcon_r 00 00 00]
```

The round constants begin:

```text
Rcon1 = {01 00 00 00}
Rcon2 = {02 00 00 00}
Rcon3 = {04 00 00 00}
Rcon4 = {08 00 00 00}
Rcon5 = {10 00 00 00}
Rcon6 = {20 00 00 00}
Rcon7 = {40 00 00 00}
Rcon8 = {80 00 00 00}
Rcon9 = {1B 00 00 00}
Rcon10= {36 00 00 00}
```

The `g` function provides nonlinearity and round dependence in the key schedule.

---

## 10. Construction of the AES S-box and IS-box

### S-box construction

For each byte `a` in `GF(2^8)`:

1. If `a != 0`, compute its multiplicative inverse `a^-1` in `GF(2^8)`; map zero to zero.
2. Apply the AES affine transformation over `GF(2)`.
3. Add the constant `{63}` by XOR.

A bit-level form of the affine transformation is:

```text
b_i = a_i XOR a_(i+4) XOR a_(i+5) XOR a_(i+6) XOR a_(i+7) XOR c_i
```

with indices modulo 8 and constant byte `c = {63}`. The result is the S-box output.

### IS-box construction

The inverse S-box reverses the two operations:

1. Apply the inverse affine transformation, including the inverse constant operation.
2. Compute the multiplicative inverse again in `GF(2^8)`; zero maps to zero.

```text
S-box:  GF(2^8) inverse -> affine transform -> {63} XOR
IS-box: inverse affine transform -> GF(2^8) inverse
```

The S-box and IS-box are permutations and satisfy:

```text
ISBOX(SBOX(x)) = x
SBOX(ISBOX(x)) = x
```

---

## 11. DES and AES comparison

| Property | DES | AES |
|---|---:|---:|
| Standardization | NBS/NIST FIPS PUB 46, 1977 | NIST, 2001 |
| Cipher family | Feistel network | Substitution-permutation network |
| Block size | 64 bits | 128 bits |
| Effective key size | 56 bits | 128, 192 or 256 bits |
| Number of rounds | 16 | 10, 12 or 14 |
| Data representation | Two 32-bit halves | 4 x 4 byte State |
| Round key size | 48 bits | 128 bits used per AES round |
| Main nonlinear step | Eight DES S-boxes after expansion/XOR | One S-box applied to every State byte |
| Diffusion | Expansion and permutation in Feistel round | ShiftRows plus MixColumns |
| Final-round special rule | Feistel convention includes final swap/preoutput | MixColumns omitted in final encryption round |
| Decryption | Same network with reversed subkeys | Inverse transformations with reversed round keys |
| Current security status | 56-bit key is inadequate for modern protection | Current standard family; select key size and mode appropriately |

Short conclusion: DES is historically important because it demonstrates a practical Feistel design, but AES gives a larger block and substantially larger key choices with a clearer byte-oriented transformation structure.

---

## 12. Exam answer templates

### “Explain Feistel encryption and decryption”

Write the split diagram, state

```text
L_i = R_(i-1)
R_i = L_(i-1) XOR F(R_(i-1),K_i)
```

then explain that decryption uses the same structure with `K_n` first and `K_1` last. Mention the final swap convention.

### “Illustrate DES encryption”

Draw `IP -> 16 Feistel rounds -> swap -> IP^-1`, and beside it draw `PC-1 -> C0,D0 -> shifts -> PC-2 -> K1...K16`. State 64-bit block and 56-bit effective key.

### “Illustrate AES encryption”

Draw `Load State -> AddRoundKey -> 9 full rounds -> final round -> ciphertext`. Explicitly write:

```text
full round = SubBytes -> ShiftRows -> MixColumns -> AddRoundKey
final round = SubBytes -> ShiftRows -> AddRoundKey
```

### “Explain any two AES transformations”

Use `SubBytes` and `ShiftRows` for the easiest descriptive answer, or `MixColumns` and `AddRoundKey` when equations are expected. Always mention that AES bytes are arranged column-major.

---

## 13. Verification ledger

| Item checked | Evidence/source | Status and handling |
|---|---|---|
| Module scope | `F:\SeventhSem\Cryptography\MODULE 2 a crypto.pdf`, p.1; question bank, lines 53–78 | Covers block/stream, Feistel, DES and AES topics requested. |
| Stream cipher definition | Module 2 notes, p.1, lines 19–28 | Bit/byte operation and keystream requirement retained. |
| Block cipher definition | Module 2 notes, p.1, lines 29–33 | Fixed-size whole block and equal-length ciphertext retained. |
| Reversibility motivation | Module 2 notes, p.1, lines 34–40 | Nonsingular mapping requirement retained. |
| Substitution/permutation | Module 2 notes, pp.4–5, lines 103–118 | Definitions retained. |
| Confusion/diffusion | Module 2 notes, p.5, lines 119–157; p.6, lines 165–166 | Shannon terminology and purposes retained. |
| Feistel structure | Module 2 notes, p.6, lines 169–188 | Split, round function, XOR and swap retained. |
| Feistel design parameters | Module 2 notes, p.6, lines 190–207; p.7, lines 217–226 | Block/key size, rounds, subkeys, F, speed and analysis retained. |
| Feistel decryption | Module 2 notes, pp.9–10, lines 239–303 | Reverse subkey order and XOR cancellation retained. |
| DES parameters | Module 2 notes, pp.10–12, lines 305–363 | 64-bit block, 56-bit effective key, 16 rounds, IP/IP^-1 and reversed keys retained. |
| AES standard and sizes | `F:\SeventhSem\Cryptography\module 2b  AES.pdf`, p.2; extracted text p.2 | NIST 2001, 128-bit block, 128/192/256-bit keys retained. |
| AES State and column ordering | AES notes, p.4 | 4 x 4 byte State and column-major loading retained. |
| AES round transformations | AES notes, p.5 | SubBytes, ShiftRows, MixColumns and AddRoundKey retained. |
| SubBytes lookup | AES notes, p.9 | Nibble indexing and `{95}->{2A}` example retained. |
| ShiftRows direction | AES notes, p.14 | Left shifts 0/1/2/3; inverse right shifts retained. |
| AddRoundKey | AES notes, p.25 | Bytewise XOR, inverse by XOR and reversed keys retained. |
| Key expansion | AES notes, pp.29–30 | AES-128 44 words and `w4=g(w3) XOR w0` pattern retained. |
| `g` function | AES notes, p.29 plus standard AES schedule | RotWord, SubWord and Rcon retained. |
| S-box/IS-box construction | Question bank, line 75; standard AES finite-field construction | Forward and inverse construction described without inventing table values. |
| AddRoundKey numerical matrices | Question bank, lines 76–78 | **UNRESOLVED:** source contains `[pic]` placeholders; no matrix/result guessed. |
| AES final-round ordering | Cross-check against AES standard algorithm | `MixColumns` correctly omitted in final encryption round; inverse omitted in final inverse round. |

### Source limitation

The local question-bank text explicitly preserves the Add Round Key question but only as image placeholders. This draft intentionally marks that numerical item unresolved rather than fabricating matrices or a result. No source file outside the requested temporary draft was modified.

---

# Cryptography — Module 3 Core + Insurance Draft

## Scope and exam use

This draft follows the locally supplied teacher question bank (`crypto_question_bank.txt`), Module 3: **Public Key Cryptography and RSA**. It uses the standard public-key treatment and notation used in William Stallings, *Cryptography and Network Security*. The ten bank prompts are answered below in exam-ready form. Words in **bold** are useful scoring points; diagrams are intentionally ASCII so they can be reproduced quickly in an answer booklet.

---

# Part A — Core answers for every teacher-bank question

## Q1. What are the roles of the public and private key?

An asymmetric cryptosystem uses a related pair of keys:

- **Public key:** openly distributed. It is used by other people to encrypt a message for the owner or to verify a signature made by the owner.
- **Private key:** kept secret by the owner. It is used to decrypt messages encrypted with the matching public key or to create a digital signature.

The two keys are mathematically related, but deriving the private key from the public key must be computationally infeasible for a secure system.

### Two basic uses

**1. Confidentiality (encryption):**

```text
Sender                         Receiver B
M -- encrypt with PU_B --> C -- decrypt with PR_B --> M
                                  PR_B is secret
```

Only B can recover `M`, because only B possesses `PR_B`.

**2. Authentication/signature:**

```text
Sender A                         Receiver B
M -- sign with PR_A --> S -- verify with PU_A --> accept/reject
                                  PU_A is public
```

Anyone can verify that the signature was made using A's private key. In practice, a signature also requires hashing and certificate-based identity binding.

**Important distinction:** public-key encryption gives confidentiality when the receiver's public key is used; private-key signing gives authentication/integrity/non-repudiation when the sender's private key is used. Real systems normally use a hybrid design: public key for key establishment or signatures and a fast symmetric cipher for bulk data.

---

## Q2. Describe the terminology related to asymmetric encryption

### (i) Asymmetric keys

An **asymmetric key pair** is `(PU, PR)`, consisting of a public key and its matching private key. They are generated together and have complementary operations. The private key must never be disclosed. Security rests on a one-way or trapdoor mathematical problem, not on hiding the public key.

### (ii) Public-key certificate

A **public-key certificate** is a digitally signed data record that binds an identity to a public key. It normally contains:

- subject/owner name;
- subject public key and algorithm;
- issuer (the Certification Authority, CA);
- serial number;
- validity period;
- permitted key usage and extensions;
- CA's digital signature.

```text
Identity + Public key + Validity + Usage
                    |
              signed by CA
                    v
             Public-key certificate
```

A verifier checks the CA signature and the certificate chain before trusting the key.

### (iii) Public-key (asymmetric) cryptographic algorithm

A **public-key cryptographic algorithm** is a mathematical procedure using two related keys. Typical operations are encryption/decryption, digital signature generation/verification, and key agreement. Examples include RSA, Diffie–Hellman, ElGamal, and elliptic-curve systems.

### (iv) Public Key Infrastructure (PKI)

**PKI** is the complete set of people, policies, hardware, software, and procedures used to create, distribute, validate, revoke, and manage public-key certificates.

```text
        Registration Authority (RA)
                    |
                    v
Users --> Certification Authority (CA) --> certificates
                    |
                    v
        Repository / directory / status service
                    |
              revocation checking (CRL/OCSP)
```

The CA signs certificates; an RA may perform identity registration; repositories publish certificates; CRL/OCSP services report revoked certificates.

**Beginner idea:** a certificate is like a government-attested label saying “this public key belongs to this person/server.” PKI is the whole system that issues and checks those labels.

---

## Q3. What requirements must a public-key cryptosystem fulfill to be secure?

For a public-key cryptosystem, the following requirements are stated in the standard model:

1. **Easy key-pair generation:** It must be computationally feasible for a user to generate `(PU, PR)`.
2. **Easy encryption:** Given the public key `PU` and plaintext `M`, it must be feasible to compute ciphertext `C`:
   `C = E(PU, M)`.
3. **Easy decryption:** Given the private key `PR` and ciphertext `C`, it must be feasible to recover the plaintext:
   `M = D(PR, C)`.
4. **Correctness/complementarity:** For every valid message,
   `D(PR, E(PU, M)) = M`.
5. **Private-key infeasibility:** Knowing `PU` must not make it feasible to determine `PR`.
6. **Ciphertext/known-plaintext resistance:** Knowing `PU` and ciphertext `C` must not make it feasible to recover `M`, except by an authorized private-key operation or a computationally infeasible attack.
7. **Resistance to key-recovery attacks:** It must be infeasible to recover the private key from public information, including known plaintext/ciphertext pairs.

A modern implementation also needs secure parameter sizes, secure padding/encoding, side-channel protection, and authenticated key ownership. Textbook RSA without padding is not considered safe for real deployment.

### Core one-way idea

```text
PU and M  --easy-->  C
PR and C  --easy-->  M
PU and C  --hard-->  M or PR
```

The “hard” step is the security foundation.

---

## Q4. With a neat diagram explain the six ingredients of a public-key cryptosystem

The six ingredients are:

1. **Plaintext:** readable original data `M`.
2. **Encryption algorithm:** transforms `M` into ciphertext using a key.
3. **Public/private key pair:** `PU_A` is public and `PR_A` is secret; the pair belongs to user A.
4. **Ciphertext:** scrambled output `C`.
5. **Decryption algorithm:** recovers plaintext from ciphertext using the appropriate key.
6. **Key distribution/publication mechanism:** makes public keys available and authentic, commonly through certificates/PKI.

### Secrecy model

```text
                         Public key PU_B
                              |
                              v
Plaintext M --> [Encryption E] --> Ciphertext C
                                      |
                         insecure channel/network
                                      |
                                      v
                              [Decryption D]
                              uses private PR_B
                                      |
                                      v
                               Plaintext M

              PU_B: published       PR_B: kept secret by B
```

Equations:

`C = E(PU_B, M)`

`M = D(PR_B, C)`

### Beginner explanation

The public key is like a padlock that anyone may use to lock a box. Only the owner has the private key needed to open it. The network may be observed, but the observer cannot efficiently open the box.

---

## Q5. Describe the models of public-key encryption scheme: (i) encryption with public key and (ii) encryption with private key, with essential steps

### (i) Encryption with the public key — secrecy/confidentiality

To send a secret message to B:

1. B generates `PU_B` and `PR_B`.
2. B publishes `PU_B` and protects `PR_B`.
3. A obtains and authenticates `PU_B`.
4. A computes `C = E(PU_B, M)`.
5. A sends `C` over the channel.
6. B computes `M = D(PR_B, C)`.

```text
A: M --E(PU_B)--> C ==================> B: C --D(PR_B)--> M
       public key                         private key
```

Security goal: **confidentiality**.

### (ii) Encryption with the private key — authentication/signature model

To authenticate a message from A:

1. A keeps `PR_A` secret and publishes `PU_A`.
2. A computes `S = E(PR_A, M)` (in practice, signs a hash of M).
3. A sends `(M, S)` or sends the signature with the message.
4. B obtains/authenticates `PU_A`.
5. B computes `M' = D(PU_A, S)` or verifies the signature.
6. B accepts if the recovered/verified value matches M.

```text
A: M --E(PR_A)--> S; send (M,S) ==========> B
                                               |
                                      D/verify with PU_A
                                               |
                                      valid A signature?
```

Security goal: **authentication, integrity, and support for non-repudiation**. It does **not** provide secrecy, because `PU_A` is public.

### Practical combined operation

```text
A --signature with PR_A--> signed session-key message
A --encrypt session key with PU_B--> protected key
bulk data --symmetric encryption--> efficient encrypted data
```

---

## Q6. Compare conventional and public-key encryption schemes

| Feature | Conventional (symmetric) | Public-key (asymmetric) |
|---|---|---|
| Keys | One shared secret key | Related public and private keys |
| Key secrecy | Both parties must protect the same key | Only private key is secret; public key is publishable |
| Key distribution | Difficult: secret key must reach both parties securely | Easier publication, but public-key authenticity must be established |
| Main operations | Fast encryption/decryption | Slower mathematical operations |
| Scalability | For `n` users, about `n(n-1)/2` pairwise keys for pairwise communication | Each user generally maintains one key pair; about `n` pairs |
| Bulk data | Excellent and normally preferred | Usually inefficient for bulk data |
| Authentication | Requires a shared secret or an additional mechanism | Digital signatures directly support authentication |
| Non-repudiation | Generally not strong: both holders know the same secret | Digital signatures can support non-repudiation, subject to key control and legal context |
| Typical examples | AES, ChaCha20 | RSA, Diffie–Hellman, ElGamal, ECC |
| Security basis | Secret key and cipher resistance | Hard mathematical problems plus key authenticity |
| Typical use | Encrypt files/records/traffic | Key exchange, signatures, certificates, small secrets |

### Exam conclusion

Symmetric cryptography is fast but has the key-distribution problem. Public-key cryptography simplifies distribution and enables signatures but is computationally expensive. Modern secure protocols combine both.

---

## Q7. Describe the essential elements of a public-key encryption model: Secrecy

The **secrecy model** protects the message from an eavesdropper.

### Elements

- Sender A has plaintext `M`.
- Receiver B has public key `PU_B` and private key `PR_B`.
- A obtains B's authentic public key.
- A encrypts: `C = E(PU_B, M)`.
- The ciphertext travels over an insecure channel.
- B decrypts: `M = D(PR_B, C)`.
- An attacker may know `PU_B` and observe C, but should not feasibly obtain M.

```text
                         attacker may observe C
A                                                        B
M --> [E using PU_B] --> C =======================> [D using PR_B] --> M
          PU_B public                                   PR_B secret
```

### Correctness condition

`D(PR_B, E(PU_B, M)) = M`.

### What it provides

- **Confidentiality** against passive observation.
- It does not automatically prove that the ciphertext came from A. For sender authentication, add a signature or an authenticated protocol.

### RSA form

For RSA, the secrecy equations are:

`C = M^e mod n`, using B's public key `(e,n)`;

`M = C^d mod n`, using B's private key `(d,n)`.

Proper RSA encryption uses randomized secure padding, such as RSA-OAEP, rather than raw textbook RSA.

---

## Q8. Describe public-key encryption used to provide authentication: Authentication model

The **authentication model** uses the sender's private key so that a receiver can verify the sender's identity and message integrity.

### Essential steps

1. A computes a digest `h = H(M)`.
2. A signs the digest using `PR_A`: `S = Sign(PR_A, h)`.
3. A sends `(M,S)`.
4. B obtains the authentic `PU_A` (normally through a certificate).
5. B computes `h1 = H(M)`.
6. B verifies `S` with `PU_A`, obtaining/checking `h2`.
7. B accepts only if `h1 = h2` and the certificate/key is trusted.

```text
Sender A                                      Receiver B
M --> H --> h --Sign(PR_A)--> S                  |
|                                               |
+---------------- send (M,S) -----------------> |
                                                v
                                  H(M) and Verify(PU_A,S)
                                                |
                                     equal and valid? yes/no
```

### RSA signature form

A simplified textbook expression is:

`S = H(M)^d mod n` (sign with private exponent `d`)

`H(M) = S^e mod n` (verify with public exponent `e`).

Real RSA signatures use an encoding such as RSA-PSS and sign a hash, not the raw message.

### Services provided

- **Data-origin authentication:** evidence that the holder of A's private key signed it.
- **Integrity:** a changed message produces a different digest.
- **Non-repudiation support:** A cannot plausibly deny a valid signature if private-key control and certificate governance are sound.

### Important caution

Using A's public key to verify a signature is not the same as encrypting for secrecy. Since `PU_A` is public, anyone can perform verification/decryption of the signature operation.

---

## Q9. Describe the RSA algorithm in detail

RSA is a public-key cryptosystem whose security is related to the difficulty of factoring a large composite integer.

### A. Key generation

1. Choose two distinct large primes `p` and `q`.
2. Compute the modulus:
   `n = p q`.
3. Compute Euler's totient:
   `phi(n) = (p-1)(q-1)`.
4. Choose public exponent `e` such that:
   `1 < e < phi(n)` and `gcd(e, phi(n)) = 1`.
5. Compute private exponent `d` as the modular inverse of e:
   `e d ≡ 1 (mod phi(n))`.
6. Publish public key `(e,n)`.
7. Keep private key `(d,n)` secret. In practice, p and q are also secret.

```text
p, q primes
    |
    +--> n=pq; phi=(p-1)(q-1)
                    |
        choose e with gcd(e,phi)=1
                    |
        compute d=e^(-1) mod phi
                    |
      public (e,n)     private (d,n)
```

### B. Encryption

Represent the message as an integer `M` with `0 <= M < n` (normally after a standard padding/encoding step).

`C = M^e mod n`.

Anyone with the public key can encrypt for the key owner.

### C. Decryption

`M = C^d mod n`.

Only the private-key holder should be able to perform this efficiently.

### D. Why decryption works

Since `ed ≡ 1 mod phi(n)`, write `ed = 1 + k phi(n)`. For values relatively prime to n, Euler's theorem gives `M^phi(n) ≡ 1 mod n`. Therefore:

`M^(ed) = M^(1+k phi(n)) = M (M^phi(n))^k ≡ M mod n`.

A complete proof handles non-coprime messages using the Chinese Remainder Theorem; the algorithm is designed so the congruence holds for all valid message representatives.

### E. RSA uses

- encryption/key transport;
- digital signatures;
- hybrid protocols, where RSA protects a symmetric session key.

### F. Security and implementation notes

- The modulus must be large enough for the required security level.
- Randomized padding is essential: RSA-OAEP for encryption and RSA-PSS for signatures.
- Raw textbook RSA is deterministic and vulnerable to structural attacks.
- Private operations need side-channel and fault-attack protection.

---

## Q10. Perform RSA encryption and decryption for p=17, q=11, e=7, M=88

### Step 1: Compute n

`n = p q = 17 x 11 = 187`.

### Step 2: Compute Euler totient

`phi(n) = (17-1)(11-1) = 16 x 10 = 160`.

### Step 3: Check e

`e = 7` and `gcd(7,160)=1`, so e is valid.

### Step 4: Find d independently

We require:

`7d ≡ 1 (mod 160)`.

Extended Euclidean calculation:

```text
160 = 22(7) + 6
  7 =  1(6) + 1
  6 =  6(1) + 0
```

Back substitute:

```text
1 = 7 - 6
  = 7 - (160 - 22*7)
  = 23*7 - 160
```

Therefore:

`23(7) - 160(1) = 1`

and hence `d = 23`.

Check:

`e d = 7 x 23 = 161 = 1 + 160`, so `7 x 23 ≡ 1 (mod 160)`.

Keys:

- **Public key:** `(e,n) = (7,187)`
- **Private key:** `(d,n) = (23,187)`

### Step 5: Encrypt M=88

`C = M^e mod n = 88^7 mod 187`.

Use repeated squaring:

```text
88^2 mod 187 = 7744 mod 187 = 77
88^4 mod 187 = 77^2 mod 187 = 5929 mod 187 = 132
88^7 mod 187 = 88^4 * 88^2 * 88 mod 187
              = 132 * 77 * 88 mod 187
              = 66 * 88 mod 187
              = 5808 mod 187
              = 11
```

Therefore:

`C = 11`.

### Step 6: Decrypt C=11

`M' = C^d mod n = 11^23 mod 187`.

Repeated squaring:

```text
11^1  mod 187 = 11
11^2  mod 187 = 121
11^4  mod 187 = 121^2 mod 187 = 14641 mod 187 = 55
11^8  mod 187 = 55^2  mod 187 = 3025  mod 187 = 33
11^16 mod 187 = 33^2  mod 187 = 1089  mod 187 = 154
```

Since `23 = 16 + 4 + 2 + 1`:

```text
11^23 mod 187
= (11^16)(11^4)(11^2)(11^1) mod 187
= 154 * 55 * 121 * 11 mod 187
= 55 * 121 * 11 mod 187
= 110 * 11 mod 187
= 88
```

Therefore:

`M' = 88`.

### RSA round-trip result

```text
M=88 --encrypt with (7,187)--> C=11 --decrypt with (23,187)--> M'=88
```

The round trip is verified because `M' = M = 88`.

### Independent verification by CRT

Modulo 17:

- `88 mod 17 = 3`.
- `11^23 mod 17`: `11^2=2`, `11^4=4`, `11^8=16`, `11^16=1`; so `11^23 = 11^(16+4+2+1) ≡ 1*4*2*11 = 88 ≡ 3 (mod 17)`.

Modulo 11:

- `88 mod 11 = 0`.
- `11^23 mod 11 = 0`.

The unique value modulo `17 x 11 = 187` satisfying `x ≡ 3 (mod 17)` and `x ≡ 0 (mod 11)` is `x=88`, confirming the decryption independently.

### Marking checklist for this numerical answer

`n=187` (1); `phi=160` (1); valid e (1); `d=23` with inverse check (2); encryption method and `C=11` (2); decryption method and `M=88` (2); round-trip statement (1).

---

# Part B — Clearly labelled insurance sections

These are concise backup answers in case the paper shifts public-key topics between modules.

## Insurance 1. Diffie–Hellman key exchange

Diffie–Hellman (DH) allows two parties to establish a shared secret over a public channel. It does **not by itself authenticate** the parties and is therefore vulnerable to a man-in-the-middle attack unless combined with certificates/signatures.

### Algorithm

Publicly choose a large prime `q` and a generator `alpha` of a suitable subgroup modulo q.

1. A chooses private random `x_A`; sends `Y_A = alpha^x_A mod q`.
2. B chooses private random `x_B`; sends `Y_B = alpha^x_B mod q`.
3. A computes `K = Y_B^x_A mod q`.
4. B computes `K = Y_A^x_B mod q`.

Both obtain:

`K = alpha^(x_A x_B) mod q`.

```text
Public: q, alpha

A: private x_A                         B: private x_B
   Y_A=alpha^x_A  -------------------->
                    <------------------  Y_B=alpha^x_B
   K=Y_B^x_A                           K=Y_A^x_B
             K is the same shared secret
```

### Small illustrative example

Let `q=23`, `alpha=5`, `x_A=6`, `x_B=15`.

`Y_A = 5^6 mod 23 = 8`.

`Y_B = 5^15 mod 23 = 19`.

A: `K = 19^6 mod 23 = 2`.

B: `K = 8^15 mod 23 = 2`.

So the shared secret is `K=2` in this toy example. Real systems use large safe parameters and derive session keys through a KDF; they never use a tiny example modulus.

### Limitation: man-in-the-middle

An attacker can establish one secret with A and a different secret with B while relaying messages. Authentication of public DH values is required.

---

## Insurance 2. ElGamal public-key encryption

ElGamal is a probabilistic public-key encryption scheme based on the discrete logarithm problem.

### Key generation

1. Choose a large prime `q` and generator `alpha`.
2. Choose private key `x` with `1 <= x <= q-2`.
3. Compute `y = alpha^x mod q`.
4. Public key: `(q, alpha, y)`.
5. Private key: `x`.

### Encryption of M

Choose a fresh random number `k` for every encryption:

`C1 = alpha^k mod q`

`C2 = M y^k mod q`

Ciphertext is `(C1,C2)`.

### Decryption

Compute:

`K = C1^x mod q = alpha^(kx) mod q`.

Then:

`M = C2 K^(-1) mod q`.

```text
Public (q,alpha,y)                  private x
M + fresh k --> C1=alpha^k
             --> C2=M*y^k -------- ciphertext (C1,C2)
                                   C1^x=y^k; remove K to recover M
```

**Exam points:** randomized encryption; ciphertext has two components; fresh k is essential; message must be represented in the group; authentication is not automatic.

---

## Insurance 3. Elliptic-curve arithmetic

An elliptic curve over a finite prime field is commonly written:

`E: y^2 ≡ x^3 + a x + b (mod p)`

with the non-singularity condition:

`4a^3 + 27b^2 not≡ 0 (mod p)`.

The points on the curve plus the point at infinity `O` form an abelian group.

### Point addition

For distinct points `P=(x1,y1)` and `Q=(x2,y2)`, where `x1 != x2`:

```text
lambda = (y2-y1) (x2-x1)^(-1) mod p
x3 = lambda^2 - x1 - x2 mod p
y3 = lambda(x1-x3) - y1 mod p
P+Q=(x3,y3)
```

### Point doubling

For `P=Q` and `y1 != 0`:

```text
lambda = (3x1^2+a) (2y1)^(-1) mod p
x3 = lambda^2 - 2x1 mod p
y3 = lambda(x1-x3) - y1 mod p
2P=(x3,y3)
```

If `Q=-P=(x1,-y1 mod p)`, then `P+Q=O`. Also `P+O=P`.

### Tiny worked example

Use `E: y^2 = x^3 + 2x + 2 (mod 17)`, `P=(5,1)`, `Q=(6,3)`.

Check points:

- P: `1^2=1`; `5^3+2(5)+2=137 ≡ 1 (mod17)`.
- Q: `3^2=9`; `6^3+2(6)+2=230 ≡ 9 (mod17)`.

Add P and Q:

```text
lambda = (3-1)/(6-5) = 2 mod 17
x3 = 2^2 - 5 - 6 = -7 = 10 mod 17
y3 = 2(5-10)-1 = -11 = 6 mod 17
```

Thus `P+Q=(10,6)`. Check: `6^2=36 ≡ 2`; `10^3+2(10)+2=1022 ≡ 2 (mod17)`.

### ECC public-key idea

- Public parameters: curve E and base point G of large prime order n.
- Private key: random integer `d`.
- Public key: `Q=dG`.
- Security assumption: computing d from G and Q is the elliptic-curve discrete logarithm problem.

```text
private d --scalar multiplication--> public Q=dG
```

ECC gives comparable security with much smaller keys than classical finite-field systems, but implementation must validate points and protect against side channels.

---

# Part C — Rapid revision sheet

## Public-key answer skeleton

```text
Define -> keys -> algorithm -> equations -> diagram -> security service -> limitation/application
```

## RSA one-line memory chain

`p,q -> n=pq -> phi=(p-1)(q-1) -> choose gcd(e,phi)=1 -> d=e^(-1) mod phi -> C=M^e mod n -> M=C^d mod n`.

## Secrecy versus authentication

- **Secrecy:** encrypt using receiver's public key; decrypt using receiver's private key.
- **Authentication:** sign using sender's private key; verify using sender's public key.
- **Do not confuse:** a public key is not proof of identity until validated by a certificate/PKI.

---

# Verification ledger

| Item checked | Verification | Result |
|---|---|---|
| Local teacher-bank coverage | Module 3 contains 10 prompts: roles; terminology; requirements; six ingredients; two models; conventional comparison; secrecy; authentication; RSA; RSA numerical | All 10 covered as Q1–Q10 |
| RSA modulus | `17 x 11` | `n=187` |
| RSA totient | `(17-1)(11-1)` | `phi=160` |
| Public exponent validity | `gcd(7,160)` | `1`, valid |
| Extended Euclid | `160=22(7)+6; 7=1(6)+1` | `1=23(7)-160` |
| Private exponent | `7 x 23=161=1+160` | `d=23`, independently checked |
| Encryption square | `88^2 mod187` | `77` |
| Encryption square | `88^4 mod187` | `132` |
| Ciphertext | `88^7 mod187` | `11` |
| Decryption squares | `11^2,11^4,11^8,11^16 mod187` | `121,55,33,154` |
| Decryption | `11^23 = 11^(16+4+2+1) mod187` | `88` |
| RSA round trip | `88 -> 11 -> 88` | Pass |
| Independent CRT check | Mod 17 gives `3`; mod 11 gives `0`; `88` satisfies both | Pass |
| Insurance topics | Diffie–Hellman, ElGamal, elliptic-curve arithmetic | Clearly labelled and included |
| Scope constraint | Only requested output draft is written | This file only |

---

# Revised Question Bank Addendum - New Module 1-3 Questions

> **Source:** `Cryptography question bank new.doc`. This addendum contains only questions added or made more specific in the revised bank. Modules 4-5 are intentionally excluded from the CIE 1 route. All readable numericals below were independently recomputed.

## A. Module 1 additions

### A1. Extended Euclidean algorithm: `(1759,550)`

Find `gcd(1759,550)` and integers `x,y` such that

```text
1759x + 550y = gcd(1759,550).
```

Euclidean divisions:

```text
1759 = 3(550) + 109
 550 = 5(109) + 5
 109 = 21(5) + 4
   5 = 1(4) + 1
   4 = 4(1) + 0
```

Therefore:

```text
gcd(1759,550) = 1.
```

Back-substitution:

```text
1 = 5 - 4
  = 5 - (109 - 21(5))
  = 22(5) - 109
  = 22(550 - 5(109)) - 109
  = 22(550) - 111(109)
  = 22(550) - 111(1759 - 3(550))
  = -111(1759) + 355(550).
```

**Answer:**

```text
x = -111,  y = 355.
```

**Independent check:** `1759(-111) + 550(355) = -195249 + 195250 = 1`.

### A2. Playfair decryption with key `COMPUTER`

Use the standard `I/J` combined convention. Remove repeated letters from the key and append the unused alphabet:

```text
C O M P U
T E R A B
D F G H I
K L N Q S
V W X Y Z
```

Decryption rules: move left in the same row, move up in the same column, and use opposite rectangle corners otherwise.

#### Ciphertext `OFTIBLDHXM`

```text
OF -> WE
TI -> BD
BL -> ES
DH -> IG
XM -> NX
```

Raw plaintext: `WEBDESIGNX`.

The final `X` is padding. **Plaintext: `WEB DESIGN`.**

#### Ciphertext `MTPAECNGHAQP`

```text
MT -> CR
PA -> YP
EC -> TO
NG -> GR
HA -> AP
QP -> HY
```

**Plaintext: `CRYPTOGRAPHY`.**

## B. Module 2 addition

### B1. AES MixColumns numerical

The newly added State image matches the standard AES example first column:

```text
[D4]
[BF]
[5D]
[30]
```

MixColumns multiplies it in `GF(2^8)` by:

```text
[02 03 01 01]
[01 02 03 01]
[01 01 02 03]
[03 01 01 02]
```

Useful values:

```text
02·D4 = B3,  03·BF = DA
02·BF = 65,  03·5D = E7
02·5D = BA,  03·30 = 50
03·D4 = 67,  02·30 = 60
```

Rows:

```text
B3 XOR DA XOR 5D XOR 30 = 04
D4 XOR 65 XOR E7 XOR 30 = 66
D4 XOR BF XOR BA XOR 50 = 81
67 XOR BF XOR 5D XOR 60 = E5
```

**Resulting first column:**

```text
[04]
[66]
[81]
[E5]
```

> Image check: the first column was visually read as `D4 BF 5D 30`, the well-known Stallings/FIPS MixColumns example. If the printed teacher-bank image differs on close inspection, use the same method with the corrected bytes.

## C. Module 3 additions

### C1. RSA intercepted ciphertext: `C=10, e=5, n=35`

Factor:

```text
n = 35 = 5 x 7
phi(n) = (5-1)(7-1) = 24.
```

Find the private exponent:

```text
5d = 1 (mod 24)  =>  d = 5
```

Decrypt:

```text
M = C^d mod n = 10^5 mod 35.
10^2 mod 35 = 30
10^4 mod 35 = 25
10^5 mod 35 = 25(10) mod 35 = 5.
```

**Plaintext: `M=5`.**

Check: `5^5 mod 35 = 10`, the given ciphertext.

### C2. RSA encryption: `p=7, q=17, e=5, M=6`

```text
n = pq = 119
phi(n) = 6 x 16 = 96
gcd(5,96)=1
d = 5^(-1) mod 96 = 77
```

Encryption:

```text
C = 6^5 mod 119
6^2 = 36
6^4 = 1296 mod 119 = 106
6^5 = 106(6) = 636 mod 119 = 41.
```

**Ciphertext: `C=41`.**

Independent round-trip check: `41^77 mod 119 = 6`.

### C3. Approaches used to attack RSA

Write any well-explained set appropriate to the marks:

1. **Brute force:** try possible private keys; prevented by sufficiently large keys.
2. **Mathematical factoring attack:** factor `n` to recover `p,q`, compute `phi(n)`, then obtain `d`. RSA depends on factoring being infeasible for properly generated large moduli.
3. **Timing and other side-channel attacks:** infer private-key information from execution time, power, cache or electromagnetic leakage. Use constant-time implementations and blinding.
4. **Chosen-ciphertext/padding attacks:** exploit malleability or padding-error oracles. Use secure standardized padding such as RSA-OAEP and avoid revealing detailed errors.
5. **Fault attacks:** induce an error, especially in CRT-RSA, and use correct/faulty signatures to factor `n`. Verify CRT results before release.
6. **Weak-parameter attacks:** small private exponent, shared prime factors, reused modulus, poor random primes or textbook RSA can break security even without general factoring.

**Exam conclusion:** attacks usually target factoring, weak parameters, padding/protocol design, or implementation leakage—not the correctly used abstract RSA formula alone.

### C4. Diffie-Hellman protocol

Public values: prime `q` and primitive root `alpha`. Private keys: `x_A`, `x_B`.

```text
A computes Y_A = alpha^(x_A) mod q
B computes Y_B = alpha^(x_B) mod q
A sends Y_A --------------------------> B
A <-------------------------- sends Y_B
A computes K = Y_B^(x_A) mod q
B computes K = Y_A^(x_B) mod q
```

Both obtain `K = alpha^(x_A x_B) mod q`. The private exponents are never transmitted.

#### DH numerical 1: `q=23, alpha=7, x_A=3, x_B=5`

```text
Y_A = 7^3 mod 23 = 21
Y_B = 7^5 mod 23 = 17
K_A = 17^3 mod 23 = 14
K_B = 21^5 mod 23 = 14
```

**Public keys:** `Y_A=21`, `Y_B=17`; **shared key: `K=14`.**

#### DH numerical 2: `q=71, alpha=7, x_A=5, x_B=12`

```text
Y_A = 7^5 mod 71 = 51
Y_B = 7^12 mod 71 = 4
K_A = 4^5 mod 71 = 30
K_B = 51^12 mod 71 = 30
```

**Public keys:** `Y_A=51`, `Y_B=4`; **shared key: `K=30`.**

### C5. Why unauthenticated DH is vulnerable to MITM

```text
A                     Mallory                     B
| -- Y_A ------------> |                           |
|                      | -- Y_M1 ----------------> |
|                      | <------------------ Y_B --|
| <------------ Y_M2 --|                           |

A forms K_AM with Mallory; B forms K_MB with Mallory.
Mallory decrypts/modifies messages under one key and re-encrypts under the other.
```

The attack succeeds because plain DH proves no identity. Prevent it by authenticating the exchange with digital signatures, certificates, authenticated public keys or an authenticated key-exchange protocol.

### C6. ElGamal - exam-ready algorithm

Public parameters: prime `q`, primitive root `alpha`; receiver chooses private `x` and publishes `Y=alpha^x mod q`.

Encryption of `M` using fresh random `k`:

```text
C1 = alpha^k mod q
C2 = M Y^k mod q
Ciphertext = (C1,C2)
```

Decryption:

```text
K = C1^x mod q
M = C2 K^(-1) mod q
```

Correctness follows because `C1^x = alpha^(kx) = Y^k`. Never reuse the random `k`; reuse can reveal relationships or the private key in related ElGamal signature settings.

### C7. ECC Diffie-Hellman and elliptic-curve encryption

For a public curve and base point `G` of order `n`:

```text
A: private n_A; public P_A = n_A G
B: private n_B; public P_B = n_B G
Shared point at A = n_A P_B
Shared point at B = n_B P_A
                    = n_A n_B G
```

In practical ECDH the point is passed through a key-derivation function; its coordinates should not be used directly as an encryption key.

Textbook elliptic-curve ElGamal-style encryption of encoded point `P_m` to receiver public key `P_B=n_B G`:

```text
Choose fresh random k.
C_m = { kG, P_m + kP_B }
```

Receiver decrypts:

```text
P_m + kP_B - n_B(kG)
= P_m + k(n_B G) - n_B(kG)
= P_m.
```

Security depends on the elliptic-curve discrete-logarithm problem, correct curve/point validation, strong randomness and authenticated keys.

## Addendum priority for today

1. **Must do:** EEA `(1759,550)`, both new Playfair decryptions, both new RSA numericals and RSA attacks.
2. **High-value Module 2:** MixColumns method/result and the existing AES diagrams.
3. **First insurance:** both DH numericals plus MITM sequence.
4. **Last insurance:** memorize only ElGamal and ECC-DH steps.
5. **Skip today:** revised-bank Modules 4-5 unless the faculty explicitly expanded CIE 1.
