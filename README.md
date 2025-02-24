# Unsloth Challenges
I am working through the unsloth challenges: https://colab.research.google.com/drive/1JqKqA1XWeLHvnYAc0wzrR4JBCnq43HyH
I note here my progress so far. 
Current estimated total points: 25

My personal notes with time per task and more are available upon request. 

## Challenge Progress:


- Part A (if attempted):
  - [x] Single triton kernel (+3)
  - Speedup checks:
    - [ ] If speedup <= 1.00 (-3)
    - [x] If speedup >= 1.05 (+1)
    - [x] If speedup >= 1.10 (+2)
    - [x] If speedup >= 1.15 (+2)
  - [x] Kernel works in torch compile (+1)
    - [ ] If not (-1)
  - [x] Custom ASM works (+3)
  - [ ] Uses cache eviction (+1)
  - [ ] Tested in f16 and bf16 (+1)
    - [x] If not (-1)

State:
The custom asm is written and tested, and the kernel torch compiles and is sufficiently fast. However, the asm must still be integrated into the kernel to work on T4 bf16.

- Part B (if attempted):
  - FSDP2 works with QLoRA:
    - [ ] With torch compile (+5)
    - [ ] Without torch compile (+3)
    - [ ] Uses part A and single kernel and faster (+3)
    - Uses torchAO:
      - [ ] If torchAO slower than BnB (-3)
  - TP or PP with QLoRA:
    - [ ] With zero bubble (+3)
    - [ ] Without zero bubble (+2)
  - [ ] FSDP1 works with QLoRA (+1)
  - [x] Kaggle notebook 2 tesla t4 example (+2)
    - [ ] If not (score = 0)
  - [ ] If not attempted (-2)

State:
Tested on 2GPU setup. Initial integration of FSDP2 with QLoRA.

- Part C (if attempted):
  - Uses flex attention:
    - [ ] Dynamic sequence length works (+3)
    - [ ] If not (+1)
  - [ ] No torch compile BnB (-2)
  - [x] Use part A (+1)
  - [x] Torch compile BnB (+1)
  - Attention compiled:
    - [ ] With excessive recompilation (-3)
    - [ ] Without excessive recompilation (+2)
  - MLP compiled:
    - [ ] With excessive recompilation (-3)
    - [ ] Without excessive recompilation (+1)
  - [ ] Loss not compiled (-1)
  - [ ] Layernorms not compiled (-3)
  - Max autotune triton matmul:
    - [ ] With excessive recompilation (-2)
    - [ ] Without excessive recompilation (+2)
  - [ ] If not attempted (-1)

State:
Graph breaks down by around 50%, but training loss suffers. Currently: monkey patching bnb matmul and adjacent.
- Part D:
  - Unavailable - VLMs Data Collator
    - [#55](https://github.com/unslothai/unsloth-zoo/pull/55)
    - [#56](https://github.com/unslothai/unsloth-zoo/pull/56)

  - Unavailable - VLMs image resizing
    - [#1808](https://github.com/unslothai/unsloth/pull/1808)

  - Unavailable - GGUF Vision support
    - [#1799](https://github.com/unslothai/unsloth/pull/1799)

  - Unavailable - Support Flex Attention
    - [#1803](https://github.com/unslothai/unsloth/pull/1803)

  - Available - Support Sequence Classification
    - Rejected: [#1739](https://github.com/unslothai/unsloth/pull/1739)

  - Available - Refactor Attention

  - Unavailable - Tool Calling
    - [#1764](https://github.com/unslothai/unsloth/pull/1764)

  - Available - VLMs train only on completions
    - Rejected: [#1736](https://github.com/unslothai/unsloth/pull/1736)

  - [ ] Other issues (+1/+2, max 12)

State:
Preliminary reading of issues and PRs.

- Part E (if attempted):
  - [x] VRAM 50% reduction (+2)
  - [x] Remove float32 upcast (score = 0)
  - [x] Show CE loss works (+1)
  - [x] Show other functions work (+1)
  - [ ] Hardcoded gradients (score = 0)
  - [x] Allows dynamic chunk sizes (+1)
  - [x] Llama 1B training loss matches (+1)
    - [ ] If not (score = 0)
  - [x] GRPO memory efficient linear works (+4)

State:
Complete. 

