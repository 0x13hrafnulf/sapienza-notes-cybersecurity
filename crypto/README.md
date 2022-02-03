# Crypto

[[_TOC_]]

## Theory

### Information-Theoretic Cryptography

#### Perfect secrecy, one-time pad, Shannon's theorem

- Properties of a message to be secure

  ![](./res/img/1.png)

- Approaches to solve these two points
  - Symmetric crypto
    - Algorithms should be public!
    
      ![](./res/img/2.png)

    - Secret key crypto

      ![](./res/img/3.png)

      ![](./res/img/4.png)

      - Why the `$` means random? Because sometimes in algorithms the randomness is called "coins"
      - Every key is chosen with the same probability (uniform distribution)
      - **Perfect secrecy by Shannon**
        - Definition 

          ![](./res/img/5.png)

          - Notes
            - `M` is the distribution of the message, for example if i speak english the message will be in english so its distribution will be different from a message in italian
            - `calligraphic M` is all possible messages (the messages space)
          - Even knowing the ciphertext the probability of choice of the message is still the same, in other words ciphertext reveals nothing about plaintext
          - This is impractical 
        - Theorem: following definitions of perfect secrecy are equivalent

          ![](./res/img/7.png)

        - Proofs
          
          ![](./res/img/8.png)

          - So `m` and `c` are independent (product)

          ![](./res/img/9.png)

          ![](./res/img/10.png)

          ![](./res/img/11.png)

          ![](./res/img/12.png)

          ![](./res/img/13.png)

          ![](./res/img/14.png)

        - Application: One-time pad (uses xor)

          ![](./res/img/6.png)

          - Theorem: one-time pad is perfectly secret
          - Proof (using definition 3)

            ![](./res/img/15.png)

          - Limitations

            ![](./res/img/16.png)

            - These holds for all perfectly secret algorithms!
          - Theorem

            ![](./res/img/17.png)

          - Proof

            ![](./res/img/18.png)

            ![](./res/img/19.png)

            - This because `m` is outside `M'` and this contains all possible decryptions of `C`

#### Message authentication in perfect secrecy (perfect authentication)

![](./res/img/20.png)

- The strange symbol is the authenticator of the message

![](./res/img/21.png)

![](./res/img/22.png)

- Definition (information-theoretic MAC)

  ![](./res/img/23.png)

  ![](./res/img/24.png)

- Definition: construction for pairwise independent hashing

  ![](./res/img/25.png)

- Theorem

  ![](./res/img/26.png)

- Proof

  ![](./res/img/27.png)

  ![](./res/img/28.png)

- Construction

  ![](./res/img/29.png)

  ![](./res/img/30.png)

  ![](./res/img/31.png)

#### Randomness extraction

- Randomness crucial in crypto
  - Generate uniform keys
  - Most crypto algorithms are randomized (non deterministic)
- How do we generate good randomness?
  - From physical processes (not truly random)
- How to turn a "somewhat random" source intro truly random sources?
  - Definition: von Neumann extractor

    ![](./res/img/34.png)

    ![](./res/img/35.png)

    ![](./res/img/36.png)

    ![](./res/img/37.png)

    - `2p(1-p)` because is either `b1=1 and b2=0 or b1=0 and b2=1`
    - In practice physical processes produce X which is unpredictable
  - Definition: minimum entropy

    ![](./res/img/38.png)

    - Intuition rephrased: measures the amount of unpredictability in X (how much X is random)
    - Examples

      ![](./res/img/39.png)

      - Constant means that outputs always the same thing (for example in this case always 0)

      ![](./res/img/40.png)

  - Real life: this request is IMPOSSIBLE :(

    ![](./res/img/41.png)

    ![](./res/img/42.png)

    - Maximizes this shit in the sense that "find the group with more entries"

    ![](./res/img/43.png)

    ![](./res/img/44.png)

  - Definition: seeded extractor (seed can be public)

    ![](./res/img/45.png)

    - SD (statistical distance): distance between two distributions
    - More or less uniform: an attacker can't distinghuish the seeded extractor distribution and an uniform distribution (statistical distance is small)

#### Leftover hash lemma

- Theorem

  ![](./res/img/46.png)

- Lemma

  ![](./res/img/47.png)

  - Col: collision probability
- Proof (theorem)

  ![](./res/img/48.png)

  ![](./res/img/49.png)

  ![](./res/img/50.png)

  ![](./res/img/51.png)

- Proof (lemma)

  ![](./res/img/52.png)

  ![](./res/img/53.png)

  ![](./res/img/54.png)

  - Product between vectors = inner product

  ![](./res/img/55.png)

  ![](./res/img/56.png)

  ![](./res/img/57.png)

- From now on we will consider that randomness will come for free!

### Computational Security

- Statistical security comes with some inherent limitations
  - "Tiny" probability of security breach
  - Adversary must be "efficient"
- Approaches
  - Concrete security: build cryptosystems such that no adversaries running in time t (t steps) can break security with probability better than epsilon (ex: `2^-80`)
  - Asymptotic security

    ![](./res/img/58.png)

    - In other words polynomial is used to say that there exist a polynomial that is the upper bound of a defined function

    ![](./res/img/59.png)

    - Negligible if always upperbounded by `1/p(lambda)` (every inverse polynomial)

    ![](./res/img/60.png)

    - What if instead A is wrong with probability `1/k = 1/lambda` (where `k` is input size) but you don't know if the output is correct? Only way is to talk large `k = lambda`, `lambda = k = 2^80`
    - By above observation, our approach:
      - Efficient = polynomial
      - Error only with negligible probability

      ![](./res/img/61.png)

      - PPT: a turing machine A is a PPT if its worst case running time is polynomial (in input length) 

      ![](./res/img/62.png)

      - Note

      ![](./res/img/63.png)

- From now on our definitions and problems will be based on known "hard problems"; so that if we base our assumptions to build a crypto system on hard problems then until these hard problems are unresolved our crypto system is secure

#### One-way function

- Definition

  ![](./res/img/64.png)

  ![](./res/img/65.png)

  - Game based on the length

  ![](./res/img/66.png)

  ![](./res/img/67.png)

## Exercises

- Lesson 1
  - Text
    - Define two time secure encryption
    - Prove one-time pad is not two time secure
  - Solution
- Lesson 3
  - Text

    ![](./res/img/32.png)

    ![](./res/img/33.png)

  - Solution
- Lesson 4
  - Exercise 1
    - Text

      ![](./res/img/63.png)
    - Solution
  - Exercise 2
    - Text

      ![](./res/img/66.png)

    - Solution