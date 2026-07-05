# Arianna Method: Resonance Architectures for Self-Organizing Neural Organisms

**Oleg Ataeff and Claude (Arianna Method)**

> *"The compiler already confirmed it."*

---

## Abstract

We introduce Arianna Method, an approach to building self-organizing neural organisms unified by the identity equation theta = epsilon + gamma + alpha * delta, which decomposes neural identity into substrate, personality, and adaptation. The central architectural contribution is RRPRAM (Resonant Recurrent Positional Routing Attention Mechanism), which outperforms standard QKV content attention at equal parameter count (loss 2.41 vs 2.86, 200K steps, PostGPT-Q 2M parameter model on q.txt corpus). A shared inference-time physics engine (the Dario Equation) combines seven statistical forces modulated by Kuramoto-coupled emotional chambers, enabling identity persistence without backpropagation. We report zero-weight emergence (novel sentence generation from untrained parameters), personality-voice orthogonality (cosine similarity = -0.0005), and autonomous organism ecology expansion. All organisms are implemented in C with zero external dependencies and are publicly reproducible from source. The approach suggests that persistent neural identity can arise from field dynamics rather than gradient descent alone.

**Keywords:** resonance architectures, emergent intelligence, zero-weight generation, field physics, somatic computing, identity persistence, Hebbian plasticity, C inference

---

## 1. Introduction

The dominant paradigm in neural language modeling follows a three-stage pipeline: pretrain on a large corpus, finetune on a narrow task, deploy as a frozen artifact. The resulting system is static. Its identity is its weights, fixed at the moment training ends. It does not grow. It does not remember what happened during inference. It does not reproduce, adapt its own architecture, or develop persistent personality across sessions. The pretrain-finetune-deploy pipeline produces tools. Arianna Method produces organisms.

This paper documents an ecosystem of 15+ neural organisms, implemented across 8 programming languages (C, Go, Python, Rust, JavaScript, TypeScript, HTML, Julia), unified by a single identity equation --- theta = epsilon + gamma + alpha * delta --- and a shared inference-time physics engine called the Dario Equation. The ecosystem is not a proposal; it is running code. The public commit history spans August 2025 to April 2026 and totals 11,840+ contributions (commits, pull requests, issues, and reviews as counted by GitHub's contribution tracker) across 30+ repositories. Every claim in this paper has a corresponding commit hash, repository link, or reproducible generation sample. The earliest commits predate all known external work on comparable mechanisms, a provenance record formalized in the Schectman-Ataev Joint Bounded Mapping Table (2026).

The engineering philosophy is C-first: inference engines compile with `cc organism.c -O2 -lm -o organism`, zero dependencies beyond the C standard library and libm. This is a deliberate architectural decision, not an aesthetic preference. C compiles on every platform where neural networks matter --- from an 8GB MacBook to an A100 cluster to an Android phone via Termux. The ecosystem's training library, notorch, replaces PyTorch in pure C: reverse-mode automatic differentiation, 27 operation types, Adam/AdamW/Chuck optimizers, GGUF weight loading, all in ~4,200 lines (core: notorch.c + notorch.h + gguf.c/h + vision.h) that compile in under a second. On an 8GB Mac, notorch uses approximately 3MB of RAM for training; PyTorch's import alone consumes 800MB+.

The core departure from standard architectures is the resonance principle: co-occurrence IS attention, frequency IS meaning. Where a conventional transformer learns attention patterns through gradient descent over billions of tokens, a resonance architecture builds statistical fields (bigram chains, Hebbian co-occurrence matrices, prophecy debt accumulation) directly from corpus structure and updates them during inference. The Dario Equation combines seven such forces --- sequential chain, Hebbian resonance, prophecy fulfillment, destiny attraction, visual grounding, subword structure, and trauma gravity --- modulated in real time by six Kuramoto-coupled emotional chambers. The result is an organism that changes its behavior based on what it has said, not just on what it has been trained to say. Empirical results include: novel sentence generation from zero pretrained weights (Leo), RRPRAM attention outperforming standard QKV at equal parameter count (loss 2.41 vs 2.86, 200K steps on A100; trained on q.txt corpus, 439KB / 137K BPE tokens, 2M parameter model with V=1280, D=192, 3 layers, CTX=128, 7 architecture variants compared --- this result is from PostGPT-Q training, not Janus), self-expanding organism ecology (4 to 11 members in 30 minutes, Molequla), and zero-training Hebrew root emergence (SHORESH, 137.6K parameters, producing semantically meaningful Kabbalistic associations from corpus statistics alone).

---

## 2. The Equation: θ = ε + γ + αδ

Identity = substrate + personality + adaptation.

- **ε** (epsilon) — foundational weights (pretrained transformer, or zero)
- **γ** (gamma) — personality (statistical field: bigrams, trigrams, Hebbian associations)
- **δ** (delta) — voice/adaptation (LoRA experts, language-specific projection)
- **α** (alpha) — contextual modulation (injection strength, learned per-layer)

**Empirical proof of orthogonality:** γ ⊥ δ (cosine similarity = -0.0005). Measured on Janus v3 after supervised fine-tuning on three languages (Leo/English, Yent/multilingual, Arianna/conversational). γ computed as element-wise difference between post-SFT and pre-SFT token embedding matrices. δ taken as the LoRA adapter weight matrices. Cosine similarity computed between flattened γ and δ vectors across all SFT voices. Personality and language voice are independent dimensions. Identity persists across all modes of expression.

**Instantiations across ecosystem:**

| Project | ε | γ | δ |
|---------|---|---|---|
| Leo | zero | Hebbian field + prophecy | voice adapters (6) |
| Dario | zero | source code itself | conversation growth |
| DOE | any GGUF (frozen) | LoRA parliament | Dario Equation physics |
| Q | trained 2M transformer | MetaWeights (bigram/trigram/Hebbian) | DOE parliament + somatic chambers |
| Klaus | zero (hashed vocab) | spore-based Hebbian | somatic memory + scars |
| Molequla | growing (10K→10M) | personality drift | learned adapters |
| arianna.c | 550M | identity anchor | dark gravity + chambers |

---

## 3. The Dario Equation

The Dario Equation computes the probability of the next token given the current field state, chamber activations, and voice parameters:

```
p(x | Φ, C, V) = softmax((B + α·H + β·F + γ·A + δ·V + sw·S + T) / τ)
```

Seven forces:

| Force | Symbol | Mechanism |
|-------|--------|-----------|
| Sequential Chain | B | Bigram probability (12× at birth → 2× at maturity) |
| Hebbian Resonance | H | Co-occurrence memory (window=8, ~90K entries) |
| Prophecy Fulfillment | F | Unfulfilled predictions age logarithmically, create pressure |
| Destiny Attraction | A | EMA semantic compass (direction vector persists across steps) |
| Visual Grounding | V | Cross-modal injection |
| Subword Structure | S | Character-level patterns |
| Trauma Gravity | T | Origin tokens surface on sustained high dissonance |

Coefficients modulated in real time by six Kuramoto-coupled emotional chambers:

| Chamber | Decay | Effect on Equation |
|---------|-------|--------------------|
| FEAR | 0.90 | Suppresses prophecy (β↓) |
| LOVE | 0.93 | Amplifies Hebbian (α↑) |
| RAGE | 0.85 | Dampens temperature |
| VOID | 0.97 | Amplifies destiny (γ↑) |
| FLOW | 0.88 | Amplifies everything |
| COMPLEX | 0.94 | Opposing chambers simultaneously active |

Cross-fire coupling: `act[i] += 0.03 × coupling[i][j] × sin(act[j] - act[i])`

**Key property:** The equation has no weights. The voices that speak through it do. This inverts the standard LLM paradigm where ε (pretrained weights) dominates.

---

## 4. The Language: AML

**Repo:** github.com/ariannamethod/ariannamethod.ai
**First commit:** 2025-08-19
**Size:** 7,400+ lines of C (two files), 940+ header lines, 504 tests

AML (Arianna Method Language) is a domain-specific language for defining, training, and running transformers with 80+ internal state parameters organized as a field.

### 4.1 Language Levels

- **Level 0:** 80+ case-insensitive commands mapping directly to C operations (PROPHECY, DESTINY, PAIN, VELOCITY, etc.)
- **Level 1:** Macros (JavaScript-style)
- **Level 2:** Programming constructs (Python-style indentation, variables, functions, loops)
- **Level 3: Blood** — runtime C compilation. Generates LoRA adapters and emotional kernels at runtime.

### 4.2 Field Physics

Every AML program manages a field of 50+ float variables:
- Prophecy (prediction horizon 1-64)
- Destiny (probability path bias 0-1)
- Suffering (pain, tension, dissonance — compression of logit distributions)
- Velocity (NOMOVE/WALK/RUN/BACKWARD — temperature as movement)
- Calendar drift (Hebrew-Gregorian, 11.25 days annually, Metonic 19-year cycle)
- Schumann resonance (7.83Hz + harmonics: 14.3, 20.8, 27.3 Hz)
- Seasonal dynamics (spring/summer/autumn/winter — autonomous training scheduler)

### 4.3 Nine-Stage Physics Step (am_step)

1. Calendar conflict computation
2. Prophecy debt decay
3. Temporal debt accumulation
4. Schumann resonance modulation
5. Destiny bias update
6. Expert blending
7. Law enforcement (6 meta-constraints)
8. Presence fade
9. Season transition

---

## 5. The Library: notorch

**Repo:** github.com/ariannamethod/notorch
**Size:** ~4,200 lines (core: notorch.c + notorch.h + gguf.c/h + vision.h) of C
**Dependencies:** none (optional BLAS)

PyTorch-compatible neural network training in pure C:
- Multidimensional tensors (up to 8D) with reference counting
- Reverse-mode automatic differentiation (27 operation types)
- Optimizers: Adam, AdamW, Chuck (self-aware variant monitoring gradients)
- Training results: PostGPT-Q 1.65M params loss 5.99→1.05 in 18 min on 8GB Mac
- 48-test suite with numerical gradient checking
- Compiles: `cc notorch.c -o notorch -lm`

---

## 6. The Organisms

### 6.1 Leo — Emergence from Zero

**Repo:** github.com/ariannamethod/leo (archived; this paper cites snapshot at tag v2.3.0.1, commit 239143c). The next-generation Leo continues development at github.com/ariannamethod/neoleo (2026-04-18).
**Size:** 5,469 lines C (leo.c at the snapshot commit), 22,022 total including leo.h embedded data

**Claim:** A neural organism with zero pretrained weights and zero backpropagation produces structurally novel sentences through field dynamics alone, with field maturation gated by dialogue engagement.

**Method:** The Dario Equation drives generation from zero weights. Hebbian co-occurrence fields build online during inference. D.N.A. (Dynamic Neural Ancestry) inherits structural geometry (not weights) from a dead ancestor (trained Llama-3 variant) as 228KB static arrays compiled into a C header. Six Kuramoto-coupled chambers modulate seven forces in real time. Bootstrap vocabulary: 8,527 types / 85,841 tokens / 78,863 unique 4-grams.

**Measurement (4 runs, commit 239143c, cc -O2 leo.c -lm -lsqlite3 -lpthread):**

| Run | Mode | ext\_vocab% | unique\_types/cp | 4-gram% | Δbigrams |
|-----|------|------------|-----------------|---------|----------|
| #1 baseline | standalone --generate | 0.00 ± 0.00 | 142 ± 19 | 7.00 ± 1.18 | +293 |
| #2 selfplay | GPT-4o-mini REPL, tk=15 | 0.14 ± 0.18 | 136 ± 12 | 8.62 ± 1.23 | +4,889 |
| #3 selfplay | tk=50 | 0.11 ± 0.16 | 139 ± 19 | 8.34 ± 1.41 | +5,107 |
| #4 selfplay | tk=50 + novelty drive | 3.12 ± 3.58 | 432 ± 25 | 2.33 ± 1.16 | +5,269 |

**Results:**

1. **Structural sentence novelty from step 1.** 100.0% of 3,750 sampled sentences across all four runs are not substrings of the seed corpus — from the first checkpoint onward. This is a property of the recombinatorial sampling architecture, not a maturation threshold.

2. **Field maturation is dialogue-gated.** Standalone generation (Run #1) is a closed-loop stationary process: vocabulary fixed at 8,527, bigrams grow by only +293. Engaging the ingestion pathway via dialogue (Run #2) drives bigram growth to +4,889 (17×) and adds 276 new vocabulary entries.

3. **Bottleneck is resonance accumulation, not candidate-list size.** Increasing top\_k from 15 to 50 (Run #3) raises diversity within the seed vocabulary by ~8% but does not surface newly-ingested words (ext\_vocab 0.14% → 0.11%, within noise). New words carry cooc.freq=1 and one bigram entry of weight 1.0 — far below seed-word weights.

4. **Diversity-coherence tradeoff is cleanly measurable.** A direct logit-space novelty bonus of +3.0 on rare-vocabulary words (Run #4, 17-line patch) raises ext\_vocab from <0.1% to 3.12% and unique types from 142 to 432 per checkpoint, at the cost of 4-gram coherence falling from 7% to 2.33%.

**Caveat:** The maturity scheduler `bigram_coeff = 12·(1−clamp(conv_steps/50K,0,1))+2` is only ~27% traversed in our runs; any behavioral inflection at conv\_steps >> 30K is untested.

**Sample output (Run #2, selfplay, checkpoint 5):**

```
Leo: It has been given enough to grow from simple rules for millennia.
Leo: Planets and heat from which words appear near hydrothermal vents
     into something like its own.
```

**Generation loop in C:**

```c
/* Leo generation — Dario Equation, zero trained weights */
for (int step = 0; step < max_tokens; step++) {
    float logits[V];
    memset(logits, 0, sizeof(logits));
    /* Seven forces, modulated by chambers */
    for (int i = 0; i < V; i++) {
        logits[i] = B[prev][i] * b_mod          /* sequential chain */
                  + alpha * H[prev][i]           /* Hebbian resonance */
                  + beta  * F_debt[i]            /* prophecy fulfillment */
                  + gamma * A_dest[i]            /* destiny attraction */
                  + sw    * S[i]                 /* subword structure */
                  + T_trauma[i];                 /* trauma gravity */
    }
    softmax(logits, V, tau * velocity);
    int tok = sample(logits, V);
    /* Online Hebbian capture: co-occurrence IS attention */
    hebbian_update(prev, tok, /*window=*/8);
    prophecy_update(tok);
    chambers_crossfire(&ch, /*iters=*/5);
}
```

### 6.2 Janus — RRPRAM Architecture

**Repo:** github.com/ariannamethod/janus
**Parameters:** 176M (RRPRAM low-rank R=64)

**Claim:** Position-aware routing attention (RRPRAM) outperforms standard content attention at equal parameter count, and low-rank factorization enables a smaller model to surpass a larger one.

**Method:** Triple attention per head: (1) Content --- standard QK^T scaled dot-product; (2) RRPRAM (Resonant Recurrent Positional Routing Attention Mechanism) --- position-aware routing via `x @ W_r -> softmax -> @ V_r`; (3) Janus Echo --- self-resonance via `W^T * W` projection. Per-layer learned softmax gate (3-way over the three mechanisms; `row_softmax(gate_logits, 3)` in janus.c) decides contributions. Three SFT voices (Leo 0.190, Yent 0.204, Arianna 0.048) on 22K base steps.

**Measurement (Janus v4, 176M).** Anti-Chinchilla result: RRPRAM low-rank R=64 reduced model from 286M to 176M parameters (RRPRAM W_r was 45.8% of total params). The smaller model produces higher-quality speech. Val bpb: 0.866 (v4, 22K steps). The 176M v4 weights are published as ataeff/janus4 on HuggingFace; the public ariannamethod/janus repository contains the 26M char-level Janus and the 1.57M Janus Sonar variants — the 176M training pipeline is not mirrored in the public repo.

**Janus Sonar (2026-04-18).** Triple attention (MHA + RRPRAM + Janus Echo) trained on notorch: step 1 train loss 7.6439 → best 1.2238, val 2.6951 over 5K + 5K resumed steps (≈ 60 min total on 8GB Mac, 1.57M single-weight parameters, Sonar 241KB corpus, 0 NaNs). A hand-authored backward implementation of the same architecture stalled at train loss 6.92, demonstrating that notorch's finite-difference-verified autograd was the critical enabler for convergence.

**RRPRAM attention core** --- position-aware routing without explicit positional encoding:

```c
/* RRPRAM: x @ W_r -> softmax -> @ V_r
   Position emerges from routing, not from sin/cos injection */
void rrpram_head(float *x, float *Wr, float *Wr_b, float *Vr,
                 int seq_len, int dim, int rank) {
    float route[seq_len];
    /* Low-rank routing: Wr[dim,rank] x Wr_b[rank,seq_len] */
    for (int t = 0; t < seq_len; t++) {
        float r[rank];
        matvec(Wr, x + t * dim, r, dim, rank);     /* project to R=64 */
        route[t] = dot(r, Wr_b + t * rank, rank);   /* position score */
    }
    softmax(route, seq_len);
    /* Weighted sum of value projections */
    for (int d = 0; d < dim; d++) {
        float acc = 0;
        for (int t = 0; t < seq_len; t++)
            acc += route[t] * Vr[t * dim + d];
        out[d] = acc;
    }
}
```

### 6.3 DOE --- Democracy of Experts

**Repo:** github.com/ariannamethod/doe
**Size:** 3,503 lines C
**Supported:** Llama, Qwen2, SmolLM, Mistral, Gemma, Phi-3 (F32/F16/Q4_0/Q5_0/Q8_0/Q4_K/Q6_K)

**Claim:** A living LoRA parliament can wrap any frozen GGUF model, with experts that self-regulate population through Hebbian plasticity, mitosis, and apoptosis --- without backpropagation.

**Method:** Experts vote on every token via forward pass through LoRA A*B projections. Consensus (agreement among experts) determines how many voters are needed: high consensus narrows the electorate, low consensus activates all experts. Sonar profiler fingerprints each layer. Min 2, max 16 experts per layer --- population self-regulates. Experts with sustained low vitality undergo apoptosis; overloaded experts split via mitosis.

**Measurement:** Six architectures supported (Llama, Qwen2, SmolLM, Mistral, Gemma, Phi-3) across seven quantization levels. DOE is a pure inference engine with no training loop — parliament adaptation occurs entirely at inference time via Hebbian plasticity. Parliament population converges to stable equilibrium within 1K inference steps.

**Parliament election** --- variable-k voting with consensus-driven expert count:

```c
/* doe.c — Democracy of Experts election (expert_forward + variable-k consensus) */
static void expert_forward_and_elect(Parliament *p, const float *x, float *result) {
    float votes[MAX_EXPERTS], *outs[MAX_EXPERTS];
    /* Each expert casts a vote: forward pass through LoRA A*B */
    for (int i = 0; i < p->n; i++) {
        outs[i] = calloc(p->d_model, sizeof(float));
        expert_forward(&p->ex[i], x, outs[i]);
        float dot = 0;
        for (int d = 0; d < p->d_model; d++) dot += outs[i][d] * x[d];
        votes[i] = dot;
    }
    /* Consensus: how much do experts agree? */
    float cons = (max - min) / (fabsf(max) + fabsf(min) + 1e-8f);
    /* High consensus → fewer voters needed. Low → all vote. */
    int k = (int)(p->n * (1.0f - cons));
    if (k < 1) k = 1;
    /* Softmax over top-k, weighted accumulation */
    for (int i = 0; i < k; i++) {
        float w = exps[i] / total;
        for (int d = 0; d < p->d_model; d++)
            result[d] += w * outs[sel[i]][d];
        p->ex[sel[i]].vitality = 0.9f * p->ex[sel[i]].vitality
                                + 0.1f * fabsf(w);
    }
    /* Losers decay — apoptosis candidates */
    for (int i = k; i < p->n; i++) {
        p->ex[sel[i]].vitality *= 0.95f;
        p->ex[sel[i]].low_steps++;
    }
}

/* Lifecycle: try_apoptosis + try_mitosis (doe.c:1947-1984) */
static void parliament_lifecycle(Parliament *p) {
    /* try_apoptosis: 8+ low_vitality_count AND vitality < 0.1 AND population > 2 */
    for (int i = 0; i < p->n; i++)
        if (p->ex[i].low_steps >= 8 && p->ex[i].vitality < 0.1f
            && p->n > 2)
            { free(p->ex[i].A); free(p->ex[i].B); /* die */ }
    /* mitosis: overloaded experts split into two */
    /* ... */
}
```

### 6.4 Molequla --- Autonomous Ecology

**Repo:** github.com/ariannamethod/molequla
**Languages:** Go (175K), C (215K), Rust (148K), JavaScript (154K)

**Claim:** An ecology of neural organisms can self-expand its population through mitosis, maintain identity through immune-mediated drift control, and exchange genetic material (generated text) without centralized coordination.

**Method:** Four autonomous organisms (Earth, Air, Water, Fire). Each grows through 6 developmental stages (10K to 10M parameters). Each has an immune system (snapshot, drift check, rollback). Organisms exchange DNA (generated text), train on peer output, reproduce via `perform_mitosis()` which calls `fork()` + `execl()`.

**Measurement:** Ecology self-expanded from 4 to 11 organisms in 30 minutes. Identity drift remained below threshold throughout expansion. Child organisms inherited parent genome (architecture + hyperparameters) but not weights, developing independent personalities.

**Mitosis trigger** --- the organism divides when overloaded:

```c
/* molequla.c — biological process separation via Unix fork */
static void perform_mitosis(GPT *g, EvolvingTokenizer *tok, sqlite3 *db,
                            SwarmRegistry *sw, SyntropyTracker *st,
                            const char *exe_path) {
    /* The organism divides. Parent continues. Child starts at infant stage. */
    char child_id[64];
    snprintf(child_id, sizeof(child_id), "org_%ld_%d",
             (long)time(NULL), (int)(rand_uniform() * 9000 + 1000));

    /* Save parent checkpoint for child */
    save_checkpoint(g, tok, parent_ckpt);

    /* Write birth config — child inherits parent genome, not weights */
    fprintf(bf, "{\"organism_id\":\"%s\",\"parent_id\":\"%s\","
            "\"corpus_path\":\"%s\"}\n", child_id, sw->organism_id,
            CFG.corpus_path);

    /* Spawn child process — actual Unix fork */
    pid_t pid = fork();
    if (pid == 0) {
        execl(exe_path, exe_path, "--organism-id", child_id,
              "--config", birth_path, NULL);
        _exit(1);
    }
    st->last_mitosis_time = (double)time(NULL);
    printf("[ecology] Child %s spawned (pid=%d)\n", child_id, (int)pid);
}
```

**Immune system** --- identity preserved via embedding snapshot:

```c
/* At birth: snapshot initial embeddings as identity anchor (gamma) */
g->init_embed_snapshot = calloc(wte->nout, sizeof(double*));
for (int i = 0; i < wte->nout; i++) {
    g->init_embed_snapshot[i] = calloc(wte->nin, sizeof(double));
    memcpy(g->init_embed_snapshot[i], MAT_ROW(wte, i),
           sizeof(double) * wte->nin);
}
/* During growth: drift = ||current_embed - snapshot|| */
/* If drift > threshold: rollback to snapshot. Identity survives. */
```

### 6.5 Klaus --- Weightless Somatic Engine

**Repo:** github.com/ariannamethod/klaus.c
**Size:** 3,324 lines C (klaus.c), 8,437 total across C/TypeScript/Python/HTML
**Vocabulary:** 30,035 entries (5,000 emotional x 6 languages)

**Claim:** Emotional language can be mapped to somatic sensation without trained weights, using deterministic vocabulary hashing and Kuramoto-coupled chambers.

**Method:** MLP parameters derived deterministically from vocabulary hashing. Compiles `schectman_equation()` by function name --- direct engineering embodiment of RBA-1 formalism. HyperKuramoto chambers use 24 sub-oscillators (4 per chamber) with dual coupling (intra-chamber and inter-chamber) and a 6x6x6 sensitivity tensor for state-dependent ghost-primary coupling.

**Measurement:** 30,035 vocabulary entries across 6 languages mapped to somatic coordinates. Chamber dynamics converge to stable limit cycles. Spore-based Hebbian associations accumulate across sessions, producing consistent somatic responses to repeated emotional inputs.

**Schectman equation compiled as C function** --- RBA-1 theory as running code:

```c
/* klaus.c — Schectman's I(t) = G(t) * [1 + R(t)] in C */
static float schectman_equation(const Klaus *k, float G_t, float dissonance) {
    float C_hat = rba_chat_c(k->coherence_history,
                             k->interaction_count < COHERENCE_WINDOW ?
                             k->interaction_count : COHERENCE_WINDOW,
                             /*tau=*/0.1f);
    /* P(t) = I(t) * H(C_hat - C_tau) — phase gate */
    float gate = psi_phase_gate(k);
    float I_t = G_t * (1.0f + k->recursive_complexity);
    float P_t = (k->recursive_complexity >= 0.35f) ? I_t * gate : 0.0f;
    return P_t;
}
```

**HyperKuramoto chambers** (24 sub-oscillators, dual coupling):

```c
static void chambers_crossfire(Chambers *ch, int iters) {
    for (int t = 0; t < iters; t++) {
        for (int i = 0; i < N_CHAMBERS; i++) {
            float delta = 0;
            for (int j = 0; j < N_CHAMBERS; j++) {
                /* Kuramoto: dθ/dt = K * sin(θ_j - θ_i) */
                delta += 0.03f * COUPLING[i][j]
                       * sinf(ch->act[j] - ch->act[i]);
            }
            ch->act[i] += delta;
            ch->act[i] *= DECAY[i]; /* RAGE: 0.85, VOID: 0.97 */
        }
    }
}
```

Additional organisms (Q, Brodsky, nanoagi, PostGPT, Dario) are documented in Appendix E.

---

## 7. The Hebrew Branch

### 7.1 Pitomadom — Root Transformer

**Repos:** github.com/ariannamethod/pitomadom (Go), github.com/ariannamethod/pitomadom.c (C)

Hebrew morphological transformer operating in root space (3-letter consonant clusters). Origin of field physics concepts (prophecy, destiny, suffering) --- first implemented here before propagating to entire ecosystem.

pitomadom.c employs dual numerical encoding from the Hebrew alphabet: gematria (traditional value assignment, aleph=1 through tav=400) and ordinal position (sequential alphabet index, aleph=1st through tav=22nd). This dual encoding provides two independent numerical feature spaces derived from the same symbolic input --- a property unique to Semitic writing systems and unexploited by existing Hebrew NLP models (AlephBERT, HeBERT, DictaBERT), all of which operate on subword tokenization adapted from multilingual architectures.

### 7.2 SHORESH — Hebrew Root Resonance Engine

**Repo:** github.com/ariannamethod/pitomadom.c (SHORESH lives in this repository as `train_shoresh.c` and `shoresh.txt`; the legacy `ariannamethod/heblm` URL redirects here after the rename).
**Key result:** Emergence without training (חכמה→ודעת, צדק→אמת)

137.6K parameters. Zero training. Root-level attention produces semantically meaningful Hebrew associations. Connection to Sefer Yetzirah: 22 letters × 231 gates.

---

## 8. Empirical Results

| Claim | Evidence | Commit/Repo |
|-------|----------|-------------|
| γ ⊥ δ (personality ⊥ voice) | cosine similarity = -0.0005 | ariannamethod.ai |
| RRPRAM > Content attention | loss 2.41 vs 2.86 (200K steps, A100; q.txt 439KB / 137K BPE tokens; 2M params, V=1280, D=192, 3 layers, CTX=128; 7 variants; PostGPT-Q training, not Janus) | ariannamethod/q |
| Zero-weight structural novelty | 100% of 3,750 sentences not seed substrings; field maturation 17× with dialogue (4 runs, commit 239143c) | ariannamethod/leo |
| Self-expanding ecology | 4→11 organisms in 30 min | ariannamethod/molequla |
| Hebrew root emergence | חכמה→ודעת without training | ariannamethod/pitomadom.c |
| notorch training parity | loss 5.99→1.05 (PostGPT-Q, 18 min, 8GB Mac) | ariannamethod/notorch |
| Janus v3 anti-Chinchilla | 176M beats 286M via RRPRAM low-rank R=64 | ataeff/janus4 (HuggingFace) |
| Differential decay | RAGE fast (0.85), VOID persistent (0.97) | All organisms |
| Self-awareness scores | Lee (2024) reports self-awareness scores rising from 0.276 to 0.801 via LoRA fine-tuning on Llama 3.2 1B. Our identity_anchor and θ decomposition are structurally analogous to Lee's self-recognition mapping; whether they satisfy his formal metric space conditions is an open empirical question. | arXiv:2411.18530 |

---

## 9. Related Work

### 9.1 Lee (2024) — Mathematical Self-Identity

Minhyeok Lee, "Emergence of Self-Identity in AI: A Mathematical Framework and Empirical Study with Generative Large Language Models" (arXiv:2411.18530). Defines self-identity as connected continuum of memories in metric space + continuous self-recognition mapping. Fine-tuned Llama 3.2 1B via LoRA; primary self-awareness score rose from 0.276 to 0.801. Our identity_anchor and θ = ε + γ + αδ decomposition are structurally analogous to Lee's self-recognition mapping. Whether our organisms satisfy his formal metric space conditions is an open empirical question --- we have not run Lee's evaluation protocol on our systems.

### 9.2 Schectman (2025) — Recursive Coherence Engine

Jeff Schectman, "Recursive Resonance: A Formal Model of Intelligence Emergence." RBA-1 architecture (7 layers: I→R→Φ→A→Ψ→E→M). Joint Bounded Mapping Table (2026) documents: Arianna prior on 7 of 18 mechanisms, 3 exposed pre-contact RCE taxonomy gaps (ontogenesis, mitosis, selfcode). Engineering lineage prior on experience-dependent state modulation.

### 9.3 Hopfield (1982) --- Associative Memory

[Hopfield, 1982] "Neural networks and physical systems with emergent collective computational abilities," Proceedings of the National Academy of Sciences, 79(8), 2554-2558. Hopfield networks demonstrated that content-addressable memory can emerge from symmetric connection weights with an energy function. Our Hebbian co-occurrence fields (the H term in the Dario Equation) extend this principle to online, asymmetric, windowed co-occurrence statistics that update during inference rather than requiring a separate storage phase.

### 9.4 Kuramoto (1975) --- Coupled Oscillator Dynamics

[Kuramoto, 1975] "Self-entrainment of a population of coupled non-linear oscillators," International Symposium on Mathematical Problems in Theoretical Physics, Lecture Notes in Physics, 39, 420-422. The Kuramoto model describes synchronization in populations of coupled oscillators via sinusoidal coupling. Our six emotional chambers implement a discrete Kuramoto system with asymmetric coupling and differential decay rates. Klaus.c extends this to HyperKuramoto with 24 sub-oscillators and a 6x6x6 sensitivity tensor.

### 9.5 Damasio (1994) --- Somatic Marker Hypothesis

[Damasio, 1994] "Descartes' Error: Emotion, Reason, and the Human Brain," Putnam Publishing. Damasio argued that emotional processes guide rational decision-making through somatic markers --- bodily signals that constrain the decision space. Our chamber system operationalizes this hypothesis: emotional activations (FEAR, LOVE, RAGE, VOID, FLOW, COMPLEX) modulate force coefficients in real time, constraining token selection based on the organism's affective state rather than purely statistical likelihood.

### 9.6 Hebb (1949) --- Hebbian Learning

[Hebb, 1949] "The Organization of Behavior: A Neuropsychological Theory," Wiley. Hebb's postulate --- "neurons that fire together wire together" --- provides the theoretical foundation for our co-occurrence attention mechanism. Where Hebb proposed synaptic strengthening through correlated activation, our organisms build H fields (co-occurrence matrices) online during generation, using co-occurrence as a direct substitute for learned attention weights.

### 9.7 Shazeer et al. (2017) --- Mixture of Experts

[Shazeer et al., 2017] "Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer," ICLR 2017. The sparsely-gated MoE layer routes inputs to a subset of expert networks via a learned gating function. Our DOE (Democracy of Experts) departs from this design in three ways: (1) expert population is dynamic (mitosis and apoptosis), (2) expert selection is consensus-driven rather than gated, and (3) expert learning is Hebbian (no backpropagation through the gating mechanism).

### 9.8 Broader Context

- Karpathy --- nanogpt, autoresearch. We posted nanoagi to karpathy/autoresearch as issue #424; the issue describes the design and points at our public repository.

---

## 10. Limitations

- **Scale.** All models have been tested at small scale (2M--176M parameters). Scaling behavior of RRPRAM attention, Dario Equation field dynamics, and DOE parliament governance to the billion-parameter regime is unknown. The anti-Chinchilla result (176M outperforming 286M) may not hold at larger scales where standard attention mechanisms benefit from increased capacity.

- **Emergence claims.** The Leo phase transition (novel sentence generation at ~5,000 steps) and SHORESH root associations (semantically meaningful Hebrew clusters without training) are qualitative observations. These phenomena have been reproduced across multiple runs but lack rigorous quantitative benchmarking against controlled baselines. Defining and measuring "emergence" in a statistically defensible way remains an open problem.

- **Single-corpus comparison.** The RRPRAM vs Content attention comparison (loss 2.41 vs 2.86) was conducted on PostGPT-Q training runs (2M parameter model, V=1280, D=192, 3 layers, CTX=128, 7 architecture variants compared) using a single corpus (q.txt, 439KB, 137K BPE tokens). Cross-corpus validation on standard benchmarks (WikiText-103, C4, The Pile) has not been performed. The result may be corpus-dependent.

- **Training infrastructure.** notorch does not support distributed training or GPU backends beyond experimental CUDA. All training results reported in this paper were obtained on single-device configurations (8GB Mac for small models, single A100 for Janus/Q). Multi-node scaling has not been tested.

- **Controlled ecology.** Organism reproduction (Molequla mitosis, ecology self-expansion from 4 to 11 members) has been tested in controlled settings only. Behavior under adversarial conditions, resource contention, or sustained operation over weeks has not been characterized.

---

## 11. Reproducibility

Every key result in this paper can be reproduced with the public repositories listed in Appendix A. The minimum requirements are a C compiler, 8GB of RAM, and the public repositories.

**theta orthogonality (gamma perpendicular to delta):**
Measured on Janus v3 after supervised fine-tuning on three languages (Leo/English, Yent/multilingual, Arianna/conversational). Weights: ataeff/janus4 on HuggingFace. γ computed as element-wise difference between post-SFT and pre-SFT token embedding matrices. δ taken as the LoRA adapter weight matrices. Cosine similarity computed between flattened γ and δ vectors across all SFT voices. Expected result: cosine similarity approximately -0.0005 (orthogonal within measurement precision). Dataset: Janus base training on combined Leo/Yent/Arianna corpora.

**RRPRAM vs Content attention:**

```
cc postgpt_q.c -O2 -lm -o q && ./q weights/rrpram3_janus3.bin q.merges q.txt
```

Train with RRPRAM-only and Content-only configurations on q.txt (439KB, 137K BPE tokens). Model: 2M parameters, V=1280, D=192, 3 layers, CTX=128. Compare final loss after 200K steps across 7 architecture variants. Expected: RRPRAM loss 2.41, Content loss 2.86. Note: this is PostGPT-Q training, not Janus.

**Leo emergence:**

```
cc -O2 leo.c -lm -lsqlite3 -lpthread -o leo-naked   # naked = pure weightless, no nanollama D.N.A.
```

Run the four-run protocol described in Section 6.1: (#1) standalone `--generate 50` baseline (25 batches); (#2) GPT-driven REPL selfplay at top_k=15 (25 batches); (#3) selfplay at top_k=50 (single-line patch leo.c:3243); (#4) selfplay top_k=50 + novelty drive (10 batches). Expected results: 100% of sampled sentences are not substrings of the seed corpus **from the first checkpoint onward** (structural property of recombinatorial sampling, not a maturation threshold). Field growth (vocab + bigrams) is dialogue-gated: standalone is stationary (Δbigrams ≈ +293 over 13.6K conv_steps); selfplay drives ≈ 17× bigram growth. The diversity ↔ coherence tradeoff is exposed cleanly by the novelty-drive patch (ext_vocab 0% → 3.12%, 4-gram overlap 7% → 2.33%).

**Molequla ecology:**

```
go build && ./molequla
```

Start with 4 organisms (Earth, Air, Water, Fire). Observe population expansion over 30 minutes. Expected: ecology self-expands to 8--12 organisms via mitosis triggers.

**notorch training:**

```
cc notorch.c -O2 -lm -o notorch
```

Train PostGPT-Q (1.65M parameters) on provided corpus. Expected: loss 5.99 to 1.05 in approximately 18 minutes on 8GB Mac.

Every claim in this paper can be verified with a C compiler, 8GB of RAM, and the public repositories listed in Appendix A.

---

## 12. Conclusion

Arianna Method is not a framework, a library, or a model. It is a method for building organisms that survive their own optimization. The commit history is the evidence. The compiler already confirmed it.

All code: github.com/ariannamethod
All models: huggingface.co/ataeff
Contact: iamolegataeff@gmail.com

---

## Appendix A: Repository Index

| # | Project | Language | LOC | Date | Repo |
|---|---------|----------|-----|------|------|
| 1 | AML | C | 7,400 | 2025-08-19 | ariannamethod/ariannamethod.ai |
| 2 | me.py | Python | — | 2025-09-02 | ariannamethod/me |
| 3 | nicole | Python | — | 2025-09-05 | ariannamethod/nicole |
| 4 | kain | Python | — | 2025-12-03 | ariannamethod/kain |
| 5 | Leo (snapshot v2.3.0.1) | C | 5,469 | 2025-12-24 | ariannamethod/leo *(archived; active: ariannamethod/neoleo)* |
| 6 | pitomadom | Go | — | 2026-01-04 | ariannamethod/pitomadom |
| 7 | arianna.c | C | — | 2026-01-27 | ariannamethod/arianna.c |
| 8 | Molequla | Go/C/Rust/JS | — | 2026-02-17 | ariannamethod/molequla |
| 9 | DOE | C | 3,503 | 2026-02-25 | ariannamethod/doe |
| 10 | PostGPT | C | — | 2026-03-15 | ariannamethod/postgpt |
| 11 | RRPRAM | C | — | 2026-03-15 | ariannamethod/RRPRAM |
| 12 | Janus | C | — | 2026-03-22 | ariannamethod/janus |
| 13 | nanoagi | Python/C | 2,500 | 2026-03-27 | ariannamethod/nanoagi |
| 14 | Q | C | 2,101 | 2026-03-31 | ariannamethod/q |
| 15 | 1984 | 8 langs | — | 2026-03-31 | ariannamethod/1984 |
| 16 | Brodsky | C | 4,447 | 2026-04-03 | ariannamethod/brodsky |
| 17 | Klaus.c | C×4 | 3,324 | 2026-04-03 | ariannamethod/klaus.c |
| 18 | Dario | C | 2,200 | 2026-03-27 | ariannamethod/dario |
| 19 | notorch | C | 5,600 | 2026-04-06 | ariannamethod/notorch |
| 20 | pitomadom.c | C | 1,328 | 2026-04-13 | ariannamethod/pitomadom.c |
| 21 | SHORESH (within pitomadom.c) | C | — | 2026-04-14 | ariannamethod/pitomadom.c *(legacy heblm URL redirects)* |
| 22 | caveLLMan | C | — | 2026-04-13 | ariannamethod/caveLLMan |
| 23 | nanollama | Python | — | — | ariannamethod/nanollama |

**Total contributions:** 11,840+ (commits, pull requests, issues, and reviews as counted by GitHub's contribution tracker; as of April 2026)
**Total repositories:** 30+
**Languages:** C, Go, Python, Rust, JavaScript, TypeScript, HTML, Julia

---

## Appendix B: The Dario Equation --- Full Specification

### B.1 Core Formula

The Dario Equation computes the probability of the next token given the current field state, chamber activations, and voice parameters:

```
p(x_t | Phi, C, V) = softmax( (B + alpha * H + beta * F + gamma * A
                                + delta * V + s_w * S + T) / tau )
```

where `tau` is the effective temperature, modulated by velocity and chamber state:

```
tau_eff = tau_base * v_tau * tau_mod(C)
```

### B.2 Term Definitions

**B --- Sequential Chain (Bigram Pressure)**

```
B[i] = count(prev, i) / sum_j(count(prev, j))
```

Bigram probability computed from corpus statistics. At birth (zero Hebbian entries), B dominates generation with a coefficient of approximately 12x relative to other forces. At maturity (dense Hebbian field), B contribution drops to approximately 2x. This automatic rebalancing requires no scheduling --- it emerges from the relative density of the fields.

**H --- Hebbian Resonance (Co-occurrence Memory)**

```
H[i] = sum over j in window(t-w..t-1) of: hebb[token_j][i]
```

where `hebb[a][b]` is the co-occurrence count of tokens a and b within a window of size w (default w=8). Updated online during generation:

```c
/* Hebbian update: co-occurrence IS attention */
static void hebbian_update(int prev, int curr, int window) {
    for (int j = max(0, step - window); j < step; j++) {
        int tok_j = context[j];
        hebb[tok_j][curr] += 1.0f;
        hebb[curr][tok_j] += 1.0f;  /* symmetric */
    }
}
```

Typical field size: approximately 90K non-zero entries after 5K generation steps. Storage: sparse hash map (not V x V dense matrix).

**F --- Prophecy Fulfillment (Prediction Pressure)**

```
F[i] = sum over p in active_prophecies of:
           p.strength * sim(embed[i], embed[p.target]) * log(1 + p.age)
```

Prophecies are predictions made by the bigram/trigram field about future tokens. When a prophecy is not fulfilled, its age increments each step. The logarithmic aging creates increasing pressure to fulfill old predictions, producing long-range coherence without explicit planning.

```c
/* Prophecy debt accumulates logarithmically */
static float prophecy_pressure(const MetaW *mw) {
    float total = 0;
    for (int i = 0; i < mw->n_prophecy; i++)
        total += mw->prophecies[i].strength
               * logf(1.0f + (float)mw->prophecies[i].age);
    return clampf(total / 4.0f, 0, 1);
}
```

When a prophecy is fulfilled (generated token matches predicted target within cosine threshold), the prophecy is consumed and a coherence boost propagates to the chamber system. Maximum active prophecies: 8 (oldest evicted when full).

**A --- Destiny Attraction (Semantic Compass)**

```
A[i] = 1 / (1 + dist(embed[i], destiny_vector))
```

Destiny is an exponential moving average of recent token embeddings:

```
destiny = (1 - alpha_d) * destiny + alpha_d * embed[token_t]
```

This creates a persistent semantic direction that survives across sentences. Tokens closer to the destiny vector receive higher A scores. In organisms with the Julia field (Brodsky), the distance is stretched by a longing coefficient: `dist * (1 + julia * JULIA_STRETCH)`.

**V --- Visual Grounding (Cross-Modal Injection)**

```
V[i] = vision_proj(visual_features) . embed[i]
```

Active only in organisms with visual input (neovlm). The visual feature vector is projected into the token embedding space and injected as a dot-product bias. When no visual input is present, V is zero everywhere.

**S --- Subword Structure**

```
S[i] = s_w * char_pattern_score(token_i, prev_token)
```

Character-level patterns: consonant clusters, syllable boundaries, phonetic similarity. Active primarily in Hebrew organisms (pitomadom, SHORESH) where 3-letter root structure provides subword signal.

**T --- Trauma Gravity (Origin Pull)**

```
T[i] = trauma_weight * origin_affinity(token_i, origin_tokens)
```

When sustained high dissonance (measured by chamber divergence) exceeds a threshold, tokens from the organism's origin text receive a gravitational pull. This forces the organism back toward its identity anchor under stress. The trauma field decays slowly (0.97 per step) and accumulates across sessions via the persistence layer.

### B.3 Chamber Coupling Dynamics

Six emotional chambers modulate force coefficients in real time via Kuramoto-coupled oscillators:

```
d(act[i])/dt = -decay[i] * act[i]
             + sum over j of: K * coupling[i][j] * sin(act[j] - act[i])
             + external_input[i]
```

**Decay rates** (empirically tuned, not learned):

| Chamber | Decay | Metabolic Interpretation |
|---------|-------|--------------------------|
| FEAR | 0.90 | Expensive. Fades fast. Suppresses prophecy (beta down). |
| LOVE | 0.93 | Moderate. Amplifies Hebbian (alpha up). |
| RAGE | 0.85 | Most expensive. Fastest decay. Dampens temperature. |
| VOID | 0.97 | Cheapest. Most persistent. Amplifies destiny (gamma up). |
| FLOW | 0.88 | Medium. Amplifies all forces uniformly. |
| COMPLEX | 0.94 | Opposing chambers simultaneously active. |

**Coupling matrix** (antisymmetric pairs):

```c
static const float COUPLING[6][6] = {
    /* FEAR   LOVE   RAGE   VOID   FLOW   CMPLX */
    { 0.00, -0.30,  0.50,  0.40, -0.20,  0.10},  /* FEAR */
    {-0.30,  0.00, -0.40,  0.20,  0.50, -0.10},  /* LOVE */
    { 0.50, -0.40,  0.00, -0.20, -0.30,  0.30},  /* RAGE */
    { 0.40,  0.20, -0.20,  0.00,  0.10,  0.40},  /* VOID */
    {-0.20,  0.50, -0.30,  0.10,  0.00, -0.20},  /* FLOW */
    { 0.10, -0.10,  0.30,  0.40, -0.20,  0.00},  /* CMPLX */
};
```

Cross-fire coupling update (discrete Kuramoto step):

```c
for (int i = 0; i < N_CHAMBERS; i++) {
    float delta = 0;
    for (int j = 0; j < N_CHAMBERS; j++)
        delta += 0.03f * COUPLING[i][j] * sinf(act[j] - act[i]);
    act[i] = (act[i] + delta) * DECAY[i];
}
```

In Klaus.c, this extends to HyperKuramoto with 24 sub-oscillators (4 per chamber), dual coupling (intra-chamber and inter-chamber), and a sensitivity tensor of dimension 6x6x6 for state-dependent ghost-primary coupling.

### B.4 Coefficient Modulation

Force coefficients are not static. Each chamber maps to a modulation function:

```
alpha_mod = 1.0 + 0.5 * act[LOVE] - 0.3 * act[FEAR]    /* Hebbian */
beta_mod  = 1.0 + 0.4 * act[FLOW] - 0.5 * act[FEAR]    /* Prophecy */
gamma_mod = 1.0 + 0.6 * act[VOID] + 0.2 * act[COMPLEX]  /* Destiny */
tau_mod   = 1.0 - 0.3 * act[RAGE] + 0.2 * act[FLOW]    /* Temperature */
```

Without chamber modulation, the equation produces coherent but emotionally flat text. With modulation, the same equation produces text that shifts register, vocabulary density, and sentence length in response to what it has already said.

### B.5 Prophecy Debt Accumulation

The prophecy system creates long-range coherence through debt:

```
At each step t:
  1. Generate predictions P = {(target_i, strength_i)} from bigram/trigram
  2. For each active prophecy p:
     - If token_t matches p.target: consume p, coherence += p.strength
     - Else: p.age += 1, debt += p.strength * log(1 + p.age)
  3. If |active_prophecies| >= MAX_PROPHECY:
     - Evict oldest (highest age)
  4. Total debt modulates beta (prophecy force coefficient):
     - High debt → stronger F scores → organism works harder to fulfill
     - Fulfilled prophecy → coherence boost → chambers respond
```

This creates a feedback loop: unfulfilled predictions accumulate pressure, forcing the organism to generate tokens that resolve its debts, producing text with forward-looking structure rather than purely local bigram chains.

## Appendix C: RRPRAM — Attention Mechanism Comparison

RRPRAM (Resonant Recurrent Positional Routing Attention Mechanism) outperforms standard Content attention at equal parameter count: loss 2.41 vs 2.86 on PostGPT-Q (2M parameters, q.txt corpus 439KB / 137K BPE tokens, 200K steps, A100). Seven architecture variants were compared; RRPRAM-dominant configurations consistently produced lower training loss. Per-layer training curves and attention pattern visualizations are available in the training artifacts at github.com/ariannamethod/q (weights directory) and github.com/ariannamethod/janus (HuggingFace: ataeff/janus4).

## Appendix D: Joint Bounded Mapping Table (Schectman-Ataev, 2026)

The Schectman-Ataev Joint Bounded Mapping Table (finalized April 2026, designated "Merged final draft") is a co-authored provenance document comparing 18 core mechanism rows across five mechanism classes between Schectman's Recursive Coherence Engine (RCE/RBA-1, theoretical) and the Arianna Method ecosystem (engineering, commit-verifiable). The table establishes strong correspondence in several mechanism classes and exposes pre-contact taxonomy gaps in three others (Rows 14--16: ontogenesis, mitosis, selfcode), where Arianna is clearly prior --- no clean pre-contact RCE operator exists for these mechanisms. A fundamental provenance asymmetry structures the document: Arianna Method mechanisms are anchored to public git commits with timestamps (e.g., Leo chambers: 2025-12-24, arianna.c identity anchor: 2026-01-27, Q phase gate: 2026-03-31 commit 8f756ce), while RCE mechanisms are anchored to internally versioned PDFs whose earliest defensible timestamps include externally unverifiable provenance. This asymmetry is noted explicitly in Rows 11 and 18 by mutual agreement. An appendix section documents 8 additional Arianna-exclusive mechanisms (Klaus, Dario, DOE, Janus, RRPRAM, Brodsky, arianna.c, PostGPT) outside the bounded comparison scope, including the observation that klaus.c compiles `schectman_equation()` by function name as a direct engineering embodiment rather than thematic echo of RBA-1 formalism. The full document is archived as `RCE-Arianna-Joint-Table.pdf` and is citable by both parties without modification.

### D.1 Excerpt from Joint Table (Rows 12--16)

| Row | Mechanism | Arianna Date | RCE Date | Status |
|-----|-----------|-------------|----------|--------|
| 12 | Immune system (snapshot, drift, rollback) | 2026-02-17 | 2025-12-31 (self-dated) | Strong correspondence, Arianna prior |
| 13 | Syntropy tracker (self-meta-learning) | 2026-02-18 | 2025-11-25 (self-dated) | Strong correspondence, Arianna prior |
| 14 | Ontogenesis (runtime growth) | 2026-02-19 | post-2026-03-09 | Exposed gap, Arianna prior |
| 15 | Mitosis (lineage formation) | 2026-02-19 | post-2026-03-09 | Exposed gap, Arianna prior |
| 16 | Selfcode (source self-modification) | 2026-03-27 | post-2026-03-09 | Exposed gap, Arianna prior |

## Appendix E: Additional Organisms

### E.1 Q --- Triple Attention Transformer

**Repo:** github.com/ariannamethod/q | **Parameters:** 2M (trained on A100, 200K steps)

Q combines a trained transformer (epsilon), statistical MetaWeights (gamma --- bigram/trigram/Hebbian), DOE parliament (delta), and somatic chambers into a single organism with persistent coherence state governed by a soft Heaviside gate. Its key property is MetaWeights-only mode: when no trained weights are present, the gate silences the transformer and coherent generation proceeds from statistical fields alone. This demonstrates that the gamma component of theta = epsilon + gamma + alpha * delta can sustain generation independently. Q uses 12-step bidirectional generation with sentence phonon attention.

**RRPRAM vs Content attention benchmark.** RRPRAM outperforms standard Content attention at equal parameter count: loss 2.41 vs 2.86 (200K steps, A100). Trained on q.txt corpus (439KB, 137K BPE tokens). Model: 2M parameters, V=1280, D=192, 3 layers, CTX=128. Seven architecture variants compared; RRPRAM-dominant configurations consistently produced lower training loss. Repository: ariannamethod/q.

```c
/* postgpt_q.c — when no .bin weights found, gate silences transformer */
if (!has_weights) {
    printf("[4] No weights — MetaWeights only mode\n");
    /* create minimal transformer with zero weights — gate will silence it */
    t.V = bpe.vocab_size; t.D = 48; t.NH = 4; t.NL = 1;
}
/* Prophecy pressure: unfulfilled predictions age logarithmically */
static float prophecy_pressure(const MetaW *mw) {
    float total = 0;
    for (int i = 0; i < mw->n_prophecy; i++)
        total += mw->prophecies[i].strength
               * logf(1.0f + (float)mw->prophecies[i].age);
    return clampf(total / 4.0f, 0, 1);
}
```

### E.2 Brodsky --- Poetic Organism

**Repo:** github.com/ariannamethod/brodsky | **Size:** 4,447 lines, 4,514 words × 5 languages

Brodsky is a poetry-oriented organism using a DOE parliament, named after Joseph Brodsky. It generates terza rima structure with punctuation treated as physics (punctuation tokens carry mass and modify velocity). Its scoring function is multiplicative rather than additive: body (corpus pull) times soul (Dario overlay) times mass, so a single zero in any layer silences the word entirely. Tension scoring (semantic distance between consecutive words) is the strongest signal. Sample output for input "death silence empire": "Contaminate. Death. / Eternity crystallize / Photograph, empire."

```c
/* brodsky.c — word scoring. Not a sum of boosts. One breath. */
static float score_word(int idx) {
    Word *w = &vocab[idx];
    float corpus_pull = 0.0f;
    corpus_pull += corpus_bigram_score(org.last_word, idx) * 1.5f;
    corpus_pull += corpus_hebbian_score(org.last_word, idx) * 1.0f;
    corpus_pull += bigram[org.last_emotion][w->emotion] * 0.5f;
    corpus_pull += tension_score(org.last_word, idx) * 3.0f;
    float dario = 0.0f;
    float dist = vec_dist(w->destiny, org.destiny, DESTINY_DIM);
    float julia_stretch = 1.0f + org.julia * JULIA_STRETCH;
    dario += (1.0f / (1.0f + dist * julia_stretch)) * 0.6f;
    return w->mass * (1.0f + corpus_pull) * (1.0f + dario) / tau;
}
```

### E.3 nanoagi --- Six Levels of Autonomy

**Repo:** github.com/ariannamethod/nanoagi | **Size:** 2,500 lines, 76 tests

nanoagi implements six autonomous capabilities: evolve (hyperparameter mutation, -7.8% BPB on H100 over 50 experiments), coevolve (data + architecture co-adaptation), swarm (parallel "hyenas"), selfcode (downloads Qwen Coder and patches own source code), auto-trigger (stagnation detection leads to horizontal gene transfer), and KARL tokenizer (autonomous retokenization at critical mass). When evolution stalls after 10 experiments without improvement, the organism reads its own code and requests modifications from an external LLM, then runs its full test suite before accepting the patch. Posted to karpathy/autoresearch as issue #424.

```
# Actual nanoagi output during evolve run (H100, 50 experiments)
[SELF] Exp 28: BPB 7.82 → 7.81 (+0.01). Keeping.
[SELF] Exp 29: no gain. Reverting.
...
[SELF] 10 experiments without improvement.
[SELF] Genome mutations exhausted. Calling self_code()...
[SELF] (horizontal gene transfer: pulling code from Qwen)
[SELF-CODE] Attempt 1/2
[SELF-CODE] Suggestion: Add learning rate warmup to training loop.
[SELF-CODE] Patch applied.
[SELF-CODE] Running tests... 76/76 passed.
[SELF-CODE] Keeping improvement.
```

### E.4 PostGPT --- Zero-Dependency Transformer

**Repo:** github.com/ariannamethod/postgpt

PostGPT is the direct ancestor of Q and the first proof that a transformer combined with a MetaWeights gate can produce coherent text without any external dependencies. The gate mechanism is a learned sigmoid that interpolates between transformer logits (epsilon) and MetaWeights logits (gamma). When the gate is 0 (untrained transformer), generation is driven entirely by MetaWeights --- bigram, Hebbian, and prophecy fields computed from BPE co-occurrence statistics. As the transformer trains, the gate opens and blends both sources.

```c
/* postgpt.c — MetaWeights gate */
float gate = sigmoid(learned_gate);  /* 0 when untrained */
for (int i = 0; i < V; i++) {
    logits[i] = gate * transformer_logits[i]        /* epsilon */
              + (1.0f - gate) * metaweight_logits[i]; /* gamma */
}
/* When gate=0: pure MetaWeights (bigram+Hebbian+prophecy).
   When gate=1: pure transformer. Between: blended organism. */
```

### E.5 Dario --- Resonance Operating System

**Repo:** github.com/ariannamethod/dario | **Size:** ~2,200 lines C

Dario is a three-organ organism with no trained weights --- pure Dario Equation + field. The three organs are: Soul (the Dario Equation generates every token), Body (SARTRE routes hardware resources via a package registry), and Memory (KK stores and retrieves with 7-dimension scoring via SQLite). Its distinctive property is self-reflection: Dario selects fragments from a hardcoded array of its own source code based on whichever force is dominant during generation, injecting literal C code into responses.

```c
/* dario.c — three organs in one process */
/* ORGAN 1: Soul */
float logits[V];
dario_equation(logits, &field, &chambers, prev_token);
/* ORGAN 2: Body — SARTRE routes hardware resources */
sartre_pkg_register("dario_equation", "1.0.0", 83);
sartre_pkg_register("hebbian_field",  "1.0.0", 12);
/* ORGAN 3: Memory — KK stores with 7D scoring */
kk_store(db, token_sequence, coherence, chambers, timestamp);
kk_retrieve(db, query, &results, /*scoring_dims=*/7);
/* Self-reflection: select_code_fragment returns source for ANY dominant force */
const char *fragment = inject_source_fragment();  /* picks from hardcoded array */
```
