# Educational Password Cracker — Demo (Local Only)

![warning](https://img.shields.io/badge/⚠️-Local%20use%20only-red)

**One-line:** Educational demo showing tiny brute-force & dictionary attacks on locally generated test hashes — for learning defensive password practices only.

---

## About

This repository is an educational **demo** that illustrates basic password-cracking concepts:

- tiny numeric **brute-force** (digits only, deliberately small search space)  
- a simple **dictionary attack** using a small wordlist  
- a tiny **multithreaded** brute force example  
- **salted SHA-256** test hashes (to show why salting matters)

**Important:** This code is for local learning and research only. Do **not** use it against any systems, accounts, or hashes you do not own. Misuse can be illegal.

---

## Files in this repo
├── LICENSE
├── README.md
├── .gitignore
├── create_test_hashes.py # generates local salted hashes (test_hashes.json)
├── cracker.py # demo cracker (dictionary + tiny brute force + threads)
├── small_wordlist.txt # optional local wordlist (ignored by git)
└── demo.gif # optional short demo of running the scripts (ignored by git)


> Note: `test_hashes.json` and `small_wordlist.txt` are intentionally listed in `.gitignore` so you don't accidentally push generated test data or wordlists.

---

# Quick start (VS Code friendly)

1. Open the repo folder in VS Code:
   ```bash
   code .


Create and activate a virtual environment:

Windows (PowerShell):

python -m venv .venv
.venv\Scripts\Activate.ps1


macOS / Linux:

python3 -m venv .venv
source .venv/bin/activate


Generate small sample hashes:

python create_test_hashes.py


This creates test_hashes.json (local only). The script includes a safety marker so the cracker runs only against hashes with that marker.

(Optional) create a tiny small_wordlist.txt in the repo root for faster dictionary testing. Example:

password
passw0rd
1234
admin
G00dP@ss


Run the cracker demo:

python cracker.py


The script will:
verify the safety marker in test_hashes.json
try the dictionary attack (if small_wordlist.txt exists)
try a small digits-only brute force (max length 4 by default)
try a tiny multithreaded brute force (demo only)
