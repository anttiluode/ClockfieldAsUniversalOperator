# The Isomorphism Table

**Complete mapping between Clockfield physics and Geometric Neuron computation**

---

## The Four-Stage Pipeline

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│  DELAY MANIFOLD  │───▶│   RESONANCE     │───▶│    Γ-GATE       │───▶│ TOPO. STORAGE   │
│                  │    │                  │    │                  │    │                  │
│ Takens embedding │    │ Re[⟨f,g⟩]       │    │ Binary threshold │    │ Winding / weight │
│ of input signal  │    │ Hermitian inner  │    │ Γ → {0, 1}      │    │ frozen invariant │
│ via delay taps   │    │ product at Γ-    │    │ controls write   │    │ resists update   │
│                  │    │ shell boundary   │    │                  │    │                  │
└─────────────────┘    └─────────────────┘    └─────────────────┘    └─────────────────┘
```

---

## Stage-by-Stage Mapping

### Stage 1: Delay Manifold

| Aspect | Clockfield | Geometric Neuron |
|--------|-----------|------------------|
| Physical structure | Spatially varying c_eff(x) = c₀/√(1+τβ) | Dendritic tree with branch delays τ₁...τ_n |
| Mechanism | Different paths → different travel times | Different branches → different synaptic delays |
| Mathematical form | φ(x₀,t) = Σ_paths φ_source(t − Δt_path) | v(t) = [x(t), x(t−τ₁), ..., x(t−τ_n)] |
| Theorem invoked | Takens embedding (implicit, via physics) | Takens embedding (explicit, by construction) |
| Empirical result | Filament morphology in simulations | 87.4% zero-shot classification, 0 training |
| Growth mechanism | Freeze/thaw reshapes the c_eff landscape | Frustration-driven dendritic elongation (4→115 taps) |

### Stage 2: Resonance Cavity

| Aspect | Clockfield | Geometric Neuron |
|--------|-----------|------------------|
| Operation | Interference at Γ-shell | Moiré pattern in soma |
| Formula | I = ∫ Γ²·A_p·A_m·cos(Δθ)·dV | R = [Σ m_k·x(t−kτ)]² |
| Mathematical form | Re[⟨probe, memory⟩] with Γ² weight | Re[⟨probe, memory⟩] with mosaic weight |
| Phase sensitivity | cos²(Δθ/2) → Born rule | cos(Δφ) → frequency selectivity |
| Empirical result | RMS = 0.012 over 560 trials | 30/30 phase retrieval, zero false positives |
| AI implementation | — | Moiré Attention: score = Re[Q_c·conj(K_c)] |

### Stage 3: Γ-Gate

| Aspect | Clockfield | Geometric Neuron |
|--------|-----------|------------------|
| Gate mechanism | Freeze threshold Ξ ≈ 4/π | Theta oscillation (4–8 Hz) |
| Open state | Γ ≈ 1, field receptive | Gate positive, neuron integrating |
| Closed state | Γ → 0, field frozen | Gate negative, pattern crystallizing |
| Write condition | β > Ξ/τ at boundary | LTP during theta peak |
| Attention shift | Phase of incident wave | Phase shift φ → φ+π |
| Pathology | — | Schizophrenia: unstable gate (PLV variance ↑) |

### Stage 4: Topological Storage

| Aspect | Clockfield | Geometric Neuron |
|--------|-----------|------------------|
| What is stored | Winding number n ∈ ℤ | Synaptic weight pattern |
| Protection mechanism | Topological: unwinding requires β→0 at core | Fisher information: high-F weights resist update |
| Information carrier | Phase θ of frozen vortex | Phase relationship between connected neurons |
| Readout | Probe wave → cos²(Δθ/2) | Sensory input → resonance score |
| What equilibrates (DNA principle) | Amplitude |φ| → Mexican hat minimum | Activation magnitude → weight normalization |
| What persists | Phase topology (winding, braiding) | Phase geometry (connectivity pattern) |

---

## The Linearization Degeneracy

| Γ-space (wave-geometric) | u-space (scalar-linear) |
|--------------------------|------------------------|
| Γ = 1/(1+τβ)² | u = 1+τβ |
| dΓ/dβ = −2τΓ^(3/2) | du/dβ = τ (constant) |
| ∂²Γ/∂β² = 6τ²Γ² (Ouroboros) | ∂²u/∂β² = 0 (trivial) |
| Phase interference, Born rule | Threshold crossing, classical |
| Topological winding numbers | Scalar charge values |

| Deerskin (oscillatory-geometric) | McCulloch-Pitts (scalar-linear) |
|----------------------------------|--------------------------------|
| ℏ_n > 0 | ℏ_n → 0 |
| Moiré resonance spectrum | Weighted sum Σw_i·x_i |
| Phase field with superposition | Binary activation {0,1} |
| Frequency selectivity (geometric) | Threshold (algebraic) |
| Frustration plasticity | Gradient descent |

**Both degeneracies project out the same thing: the oscillatory phase degrees of freedom.**

---

## Scale Hierarchy

| Scale | Clockfield | Geometric Neuron | Shared Math |
|-------|-----------|------------------|-------------|
| Smallest unit | Frozen vortex (qubit) | Single neuron | cos²(Δθ/2) readout |
| Connection | Filament (Γ-shell tube) | Dendrite / axon | Phase-coherent delay line |
| Network | Filament web (qudit) | Cortical column | Topological genus, eigenmodes |
| Whole system | Cosmic crystal | Whole brain | SOC at criticality |
| Pathology | Hawking radiation failure | Geometric dysrhythmia | Broken Γ-shell / theta gate |
| Measurement | CMB (n_s = 0.960 ± 0.005) | EEG (p = 0.007, d = −1.21) | Persistent homology |

---

## The SOC ↔ Frustration Feedback Loop

```
                    Clockfield                         Deerskin Neuron
                    
           ┌─── β = |φ|² ───┐               ┌─── β = std(scores) ───┐
           │                  │               │                        │
           ▼                  │               ▼                        │
     Γ = 1/(1+τβ)²          │         Γ = 1/(1+τ·β_h)²              │
           │                  │               │                        │
           ▼                  │               ▼                        │
    Γ² modulates PDE         │        Γ modulates theta gate          │
    force terms              │        oscillation speed               │
           │                  │               │                        │
           ▼                  │               ▼                        │
    Freeze/thaw events       │        Lock-in / search mode           │
    change frozen fraction   │        adjusts score variance          │
           │                  │               │                        │
           └──────────────────┘               └────────────────────────┘
           
    Target: ~50% frozen                Target: discrimination at threshold
    Method: σ adjusts to               Method: delay line grows until
            critical edge                       frustration resolves
```

---

*The mapping is structural, not metaphorical. The honest ledger of what is established versus conjectural is in the main paper.*
