# 🐍 Python File Handling — Visual Study Notes

---

# 📌 What is File Handling?

**File Handling** is the process of creating, opening, reading, writing, updating, and closing files in Python.

### 🎯 Why do we need File Handling?

Without files, data stays only in RAM.

* RAM = Temporary Storage ❌
* File = Permanent Storage ✅

---

## 🖼️ Memory vs File Storage

![Image](https://images.openai.com/static-rsc-4/POxoJ3TAd28WL8uq4QuRbHP6scSZgmSyxg_uHGB67bXWm1y8s-bduHPANMB7CxxeaI1YsrR0HZUR9dsHLLxV3JB7DSZ1Rkm-O7rVwENz0hkK8gIk93xdayBKeqPvYWJTR1qI2AaX2uW1zzKEx8k2JNtRb9_z-k5_kUc4wmQkm44uqxNr5xArhZHEput7k2z1?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/lcBEyD2LqqJxuWrfjX1kjbLQVExtXuDota5LAVqIrKffNhOwOyGuR0jtFcEXrDtWdrXymxEIVUf0FuOKIaoc0jUnaKZhtU5DETAoF0NTqBc3vGrO5f-TjUfY6P1BrcV0hRA_cfPierNOzzuuTeuVdltuFBICOGgQ2sCAVP0eiHW8zOHEPM28Yl3jUabnbbEU?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/__u2CF9rE-cDymcGSjJDGJO2Zkjyv4ugPAmtdKtsIZw0rvhOY5dDqgItTBucldXafsGM_8Sems0pjdv8M1Y4h8mRgYcNkOo0kCxcKnRq6-LMRP9dA2eYgJiGPGAQIiVhx9lFEeUP1y-4k3BhqB8PwZCLdA5tmRyj-znGNfMwE6e6-cz1xpRuhTinKSuZfGVa?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/B-QajyeAq4JvcSSs0uQ4NwxbiJSrx5bGO5pcZcTlLRR_hl8LmqIMJa9LEK7cTKPRoAV6CMt-WFZPpWPV8V83mtqmH_5W1BGU02kiSKgo3Rvls-SVc_jq5O1lPsHJBGHZfvxqGZmcaLHH2OaYbVSLIRzsLBm3IhYk9kaQ2PtqUMuLIDwrfgVAzv9xY8D0WIhE?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/FP_OjjE2PTMBcr1Q5wgVEh_FytVX0stX0sDv1WwLycAZcaluK-jFYAudSTdNLJqvaJR6agzhkd1wx4be1q2F7x0lGHfu5N7u4KvbEzhgBnhygxH3APdHQrebFjbUZJyDcgfiJZsRv9NNDFCDzPJ1GjdUVLnEG4kiyRMkuSNS4ySGmu_5Jy7to49Bw0cHrfWe?purpose=fullsize)

### Example

Imagine you write:

```python
name = "Santanu"
```

The value is stored in RAM.

When the computer shuts down:

❌ Data disappears.

But if saved in a file:

```text
name.txt
---------
Santanu
```

✅ Data remains permanently.

---

# 📌 Why Use Files?

### Real-Life Examples

![Image](https://images.openai.com/static-rsc-4/WcboN9eT31WaKPa4LvzaJ4vgFLSN2bGkivKFjiELnVUDUq2uDhErQQAOYHaJ4sy0ciQVNY_mGq3hgCMwWrh14l-MpoI4iVPm_ogy365OLmL7XaVNBXnOHLLuB8g9mDDuP3Tda43JyFPOH2ihHNIrA39eJCRblNQ0yWpviwE27wUvDAt1z0jS_jti9STbLz2a?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Ugfj81qtq0BPhmZjcAUhOHMqxBqA1lwmimf7aknR6mSh0yWxxJrS6uJJyH8kMbiREViGfuVEDunoFs_PuvTYLzwKa_z51cMUQms2O3I7esBRiXIG199yn-HpOFu6oaPoOSa6n1B-bScf6XStdWY4qUGkuM7bvwU5m9uHYwW5FmNAyOE3oNY5LtnIHPKt9D79?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/z_ZYBELwHus0LRyU9QFp7amuSoJp2zgXVZf64bIvunQWkQtA_Ybu9LBfYPlcHYxdwTFISJep_8pD6K5EmUc1-CTWz_TBqhYVYCupF-zB6ZXHkdy9sTzyFLA69Qu52CnfJ2JsEgxRyMZkboF4xOXo85iM1NkSgPVBvEFM5VUtRw6CGl70fBEEli6pHNN02JpQ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/yJ_aCHAB8wf2qNpsZGvWbbk91ZID5u3ksP2PeOj-UQM6tk3H4bG_jTlMvL0RtPTt2o3dN6vLVv914vJBBlU6j2CMRHpeueiFmoOdj1L-OXKOHdXMgFLgq9ZLV21Fvv9lx07LQNEBmx7L_eYQwCwtrxpKwkcCFXM0nnkqftKR159KeP4tJQaTRhRD7ST-PprR?purpose=fullsize)

Your computer stores everything as files:

| File Type  | Example   |
| ---------- | --------- |
| Text File  | notes.txt |
| Image File | photo.png |
| Audio File | song.mp3  |
| Video File | movie.mp4 |
| PDF File   | book.pdf  |

---

# 📌 Three Main Steps in File Handling

## 🖼️ File Handling Workflow

![Image](https://images.openai.com/static-rsc-4/egYs2jb8fxq1A4pez_L-e06o0J6ogyW6Tx9EVU-gk3O69AH4D9u3xiG5fKHXcb28nUv-PgxjpgCqBHux-t_kZfuAwKyl0HWOwrcYRM8ToBtQJC2HGyxNSc4N0kWhGHreUBNgeZFqWxKPkKXCSxi7YSG2lrNrvj4GKCjV-v6pTZuXtG_WdJeRow7awUODQLJy?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/pCUjo29A8Mk6rpdocrww-ow_pzCPQ2bwO61FDToXI2WCXQfFPdGEwDwCbNg4AmijpNcWCS0hJIcpvQaOPjex6AlwcdUuNhYJ9DOSxDIeUGRFaMG70ydba3pAuIGZpCluPHVJ7FZfpa8VhsRi5plfjLyigLtTyfBNN5BPjkyMCKkZB1rUKl0mprqYVrBUZbiw?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/3huwO0RFM9jPFdRZibDTAypyC-25HPQCbNuSxPh3HdDnhX1hxGM1N4AHLzhCw89g6MEnt-FF3Dwjo1WkgDNKj7KBmON61kqUJl0YNUQbpVGifpvyxx2VquvbqVL33NglwiHf7UCA8lr2jTE1kEMbOOYWknQK8G8blFLkgP_vplXLgVCieyLDRizjFosOnPtp?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/GZ2qRt5NOFZPtYNfXK0e7GhcXXi6mvmSOvEb0k2K5Q06RDTJRGu9CPgikzItsbD6HKbN9dJ6zmHK09YvM_K9YrXaSkogV8wPlfNGwXKSI7emGl68uY8FFSA1x9Z89S7e6X5m-FEa0DPL_rxFD5fy1K8pnGjiYltjJcGiojoHDzduNfdjpO8V1DoL9tUpRpuS?purpose=fullsize)

```text
Open File
    ↓
Read / Write / Update
    ↓
Close File
```

---

# 1️⃣ Open a File

Before using a file, Python must open it.

### Syntax

```python
f = open("data.txt")
```

### What Happens?

```text
Disk
 ↓
File Loaded
 ↓
RAM
 ↓
Python Program
```

### Example

```python
f = open("students.txt")
```

Here:

* `f` = File Handle
* `f` points to the file

---

## 🖼️ Open File Visualization

![Image](https://images.openai.com/static-rsc-4/Bl5hD3sNNBiDE-0twcHIH2qH61sJwNSTATxRnI3oZq7vt6NVS78Ls5ROZ3RJhGm0G6lqqcEaw3MLU4j2fLmx9z3PRuH5ifzGfwovvuExQWhkajXdDFZk0JoWnTVjlWMeHsSE6hvmwxy8YKY2VQ4A0AfQNa_8spPabd0uyQXmqOQjUuL_8wDrsVWUy1buwf03?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/ITWMOl8FGGTd6eEARhKHrk6axszqPHZy7Gb8P97EBGXMKtJO1C7sR-UYnrGgebQ141nqsJmN5rDO-U76OgXMa_VcOykmZq3MUfJW3xUZ3tVNnSK6TuGYWuTSdIB2GM45jrNcIIrMUD2JsCMbOX6JSfZgZMjW7UoW86RN3X2O3iDXh4FZ93Bz_ZtCxRE-ylDk?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/bxNJtZTROJkxe5o2KM_-na6vFul7l_T8heXQ4AAqwX3GoSi4sVehBKIXQBCZNe_1pgdOyziVVmaMGUXq5F3LsxA5jtsxEd26_em0wR2RtC0gor2WseezAEvsTVgjWpd29M0whuSQzf7axS5IK-3-0lkKEMMZURM4yr8AASLDT07H0Et6pZSe7E0ekdymA7iA?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/egYs2jb8fxq1A4pez_L-e06o0J6ogyW6Tx9EVU-gk3O69AH4D9u3xiG5fKHXcb28nUv-PgxjpgCqBHux-t_kZfuAwKyl0HWOwrcYRM8ToBtQJC2HGyxNSc4N0kWhGHreUBNgeZFqWxKPkKXCSxi7YSG2lrNrvj4GKCjV-v6pTZuXtG_WdJeRow7awUODQLJy?purpose=fullsize)

Think of `f` as a remote control that controls the file.

---

# 2️⃣ Read Data from File

### Syntax

```python
f.read()
```

### Example

Suppose file contains:

```text
Hello
Welcome to Python
```

Code:

```python
f = open("data.txt")

print(f.read())
```

Output:

```text
Hello
Welcome to Python
```

---

## 🖼️ Read Operation

![Image](https://images.openai.com/static-rsc-4/61bzLxw6DulMybH32N9FvZT3PuL6qTdsprPr9d7xfmk495MKmZhGB6CF2_nKmDBkLzTJJ6UA78iujKixbMa9kR3mvFmb6M_c4FVJf4oguu8trIOzG5gIAz2jiV-oCu7biRcgMf6AUfxk98QLS_WxudNPNwYsFTZOodvaIo4d18P_4AG_dL_HtU0qavW9ndEc?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/dWyDIjYQ04iEtwh1bT-gAhJnH64MHVA790TwxcsjcsG4Iw37oZD4W670MfHLndrx5NW_IgpQCtly3G8DjqREFPRgQFs4erP9jQAUBYt-Yb__RfaOFNm8qdeWHi_sjUqjXLSx8l2_js4SiTtAoS3NfFAsTpzblOd0Vi72Vw80eTBznYzQo0mHmlP0xPEV9cPE?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/hIq0G6ig8OLQxV3UWRv6Brgo-qQ2tBTQkd7cHv1MVFiz5unMSES7U6QBFVxQDtLZnhMZFz21uCjN2YeiLG0qhaG5cJjck5h4l_ORjE4scgO0uHCi2J9jp6Cgj9zhhc0WwK1SWXMhY6ZrlmVf1zQT9n0TKppArCydOUj5J3P81djVZmP40JgEBllHcsXaMHKp?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/H9u-tqrkm3qX1vOEKdTK85X13ybCl_WrlIr07NrC-CdHdhDNRGwWPSsN5NxnEpmAQw5nAaNJ6hJTDWRhCq9Ll6wfaD_2tNU9aHk2DvGz7P8JFKVxp_0V0RkO3iAUQAXKpY8oEkc7Si90JWQmcPxecq4JEN4q5ufKRO7vm7UKb0o1n1xSeNwFdZEB2VjEgcrS?purpose=fullsize)

```text
File
 ↓
Python reads content
 ↓
Display on Screen
```

---

# 3️⃣ Close File

### Syntax

```python
f.close()
```

### Why Important?

* Saves changes
* Frees memory
* Prevents corruption

---

## 🖼️ Close File Process

![Image](https://images.openai.com/static-rsc-4/mYniJ6SP9p0Jd1ewsCPezNfhlELU3z1ZdJEEXFT1t5W3I3jB-1rUyO2eZ4ATDHnqzEpn_akAT6w5d9XFDjr8xgKYRviobP2dvKFkl95sj2id4itmq8-pXTlyuoFTEd4_zwY0sqBT_CL37cuYQUQ01gEMhIRUCP7RkCVjNha0-RO0kw0VXMlqLk1YFIWBatQ4?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/KwuPtOMnFdYGrkKtZJQxrPIjWz-NrbywrJ0-F2WuXoki1p3KHNRJYkE39hqcWoKnrWE3p6dWkz3AZ2Dkl-FKdeHRLrbjAU4gG5xgwVoVKS2FLwd1igML6xfijlQ4Eo6YxLJkrc_kLfHtZB5cWXpeu8fB2l35ulMxqLbCxUNB5oUTqpFf1Wo95rvmEtoUXnGv?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/3nNWEU-zENKSOZ-Ah1hF87qzUonb3l6CpURjZyCV0rwA3YOP1sK9-UJpfq1J2x-bahpxw5nwZ8MWMABIGnm1sZW_hHhZigr1ewiWUU2anuTfy6Wi7UUMBlaABloDilf3GC0LkWtrgDRN_ZhmH_rolcjQdR5jbjXJOk88G-F4Ghp5i9o2yS_QRX5jMac0_Ngi?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/dvV7Wp-Fnesqewdl0EgJ-rinvOcIKbbwSMSNJwK2sbCAv9bdS3XTeRsLaYMQLfPy8dYhS9AC-kh-yMTk2QO5bGk4wrGuILHVvvQVIvIS_xB6PaQduB3MCeHByGU0ZcYEFaaHY_HDb1MeNOkj4ZpixnqKP-sI3diOC5pU8rHlMEi1XcxmWPozIQpL1nCH_DFb?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Me6vefdftvtguROH9B3DhqFHjvAmiJ_3jg6swpq8iLFSAKhHKQsdGmmCyUw-r81aeIxcbDG9Xian6PCZeJB6RRs4KJeXq0KQ1dCrv0bjGVhnpiR4iAumMGa4fOmrMq5Hx6CZSjYWHtPb3ErWRY1cso0mQygXJP8az3TgKkTicsJUuMf23ypcHSDUjtRMCqQ7?purpose=fullsize)

```text
RAM Changes
      ↓
Saved to Disk
      ↓
File Closed
```

---

# 📌 File Opening Modes

Python can open files in different modes.

---

# 1️⃣ Read Mode (r)

### Purpose

Read existing data.

### Syntax

```python
f = open("data.txt", "r")
```

### Features

✅ Read data

❌ Cannot write

❌ File must exist

---

## 🖼️ Read Mode

![Image](https://images.openai.com/static-rsc-4/ZRGZDnAZYkwvRF4VpceuQtVCTvHbdo3Dy6DCpTpqsFOJx3wybW2Y68p7vp1axyiEqlj9gS7MYI5Xqq6mRZH6rmfcrF0YeCzUB2Li1Z_ZFc-RoRKt9Ihbkq9yjQi09CYE-oR28lgAoXfWW_6oczpg60mFdxDZTzbhonitHk7TVLzTeysPVrEOF7QIx8NLGBEl?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/2lUdVG0H6Yy0_yN8tpUKUZF9-NdQtDjRngzgsiSfV9WS8pZ-T19ZpZ6U3XHrfv2jRO_H7mRDI2u5N4EhbZRT8oXbcnR9j48IeBgFBouAtWldORBMYzNuKHavvMQvK-MvoGHwldSLugnBrY4D1HWfzkWtxN5GD3YMRjvcBizwnKiAGOqb_mADfSN28O6UF0PV?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/h_A6h8kgx2NvmshEKolhYWU1xtyPFdNFL3xrUU0wCj-fD8i8hjQDKCb-O6M_UXRfPBLfW776dPBH0LkTFm1r2uJOt4-CfnxcJP8LBRI4luKXXUkKdRZtFUShqXlDdTkF4ug8HKwPdNPmHoDddmStKat9usDASPxo_gajWzRRFKOnRiCz-LJDtSWoNOZi2z4X?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/M9v3j3e8eVwBRIbJqYbPyBjMkpPbh9TOpQsfGAX8X9NkOLbT90PwPxzxvtBtMCtVV3PDCRkD1xxsnu_jgOb9qHphF-PAxi_Lwq4jef1KkP6RCZb0Dl6zc3ji72hgSjifuTySAg0Isy7FWk3YZSYoqw_JgfkggJGWY1MBrqHOdfGFrS838lEyOesM9W3ioWvi?purpose=fullsize)

```text
File → Read → Output
```

---

# 2️⃣ Write Mode (w)

### Purpose

Write new content.

### Syntax

```python
f = open("data.txt", "w")
```

---

### Before

```text
Hello Python
```

### Code

```python
f.write("Welcome")
```

### After

```text
Welcome
```

⚠ Old data is deleted.

---

## 🖼️ Write Mode (Overwrite)

![Image](https://images.openai.com/static-rsc-4/4EUJgbnZrhqtA5gTM_-IrO4Te3Sq_tMsRDntPOPv4zkk_hwBLncd-0qCEO3rC-JztxltVHaFxlJX2TF2kxPZYdnzj5eWgiO1AjVCTdQz5J5tAZLzTVRWfx4uPYELHmT1Jg1TM9R1nX6iLYIUunCcp8c-UQQpxcM6Nhwc7kRTvEbKoeq_dLWd5hXudVsmCC1q?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/390YAysCqK4dyOm5zSWEA2y2N_eTCcOPP3PMVjPlHQTc4JjCIQoZr-61DNSnIF53knfQcT_BhafdIh3av0kj1J5irPGJquNpka85MRuV5HiWMvkzUWYGnlH0F-aDwkAj7gTtBeoEtKcRY6deUJ2Rk1jd1P4xbU8MFZXlhAUV9QK6MggQSon4AI8kHA0ME9jH?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/ixJEHuvgOPCa-AKZ-t_kgmXDfb5tShslmyPaY0s5D65mdd8OdOz2f8ADftnfkQ-8-MU8dZzkKxuwY2rpbvH1Qja44lEwYziOqFKyVyHTjuWFShYVPFBOReA65XQim1NUuKWkjbLwtnZGaKpBgbhP0ZZ9dIt_G0NYCipzKVG9Kma7XW23rYP33B7gPYTX1txk?purpose=fullsize)

```text
Old Data
   ❌ Deleted
        ↓
New Data Written
```

---

# Difference Between Read and Write

| Read (r)        | Write (w)              |
| --------------- | ---------------------- |
| Reads file      | Writes file            |
| Cannot modify   | Can modify             |
| File must exist | Creates file if needed |

---

# 3️⃣ Append Mode (a)

### Purpose

Add data at the end.

### Syntax

```python
f = open("data.txt", "a")
```

---

### Before

```text
Python is important
```

### Code

```python
f.write("Practice daily")
```

### After

```text
Python is important
Practice daily
```

---

## 🖼️ Append Mode

![Image](https://images.openai.com/static-rsc-4/MnUyXGR1WULVNS4b7tVpRb4T7FJ-oNx3vl--rQDX8_2iA1AJ2-W0luQVenr_HMKpzU6OTw9fJpv0SJZd2U1b42hnVJm1dulzDa1amM5tz-ZR6g3-We5Z39G2Xzm5o2ODJ3SKg0oZCkPIPFtoYPu7tf-ryLgYFjhqjT4ui3lieg_FC7wgJ2GvM9ecAy0TL6BO?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/JfzDhvBGgaikwi5Hy-YL8A7ubAruNmiG2ZJeY76Ou3FQJ37hG47nwhloewrzGdAhxLaJswpx8FZhiGGI-Yc4sK7fSeMn0RkY7pTU2Ts6jQtwkaX_G56LZpL1TgbedxXY8q8oDCOrlCIVgyehgVbguUjWf8a80ScqXcp8Gh7LXJDWpgsw5k2bzcA9ynRP6LdF?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/TEafBi6W962SeromJ6eSLI65qwW3Tt79POhWW6REbvKcZPJUDq3ZMsm84P-fyxMfYPU0V04741l0slS0Q6hFFqMuHnJ36zw7AM6Negy00vNbmWBJSlOzi_rQiNa4kXjkxNO4ZtsuLhT9UNWt5rf0mLhjsY51g8YCRyZArQ-XsNGFIsKTJ_5sH6oSHE_JVPQo?purpose=fullsize)

```text
Existing Data
      +
New Data
      ↓
Combined File
```

---

# Difference: Write vs Append

| Write (w)        | Append (a)     |
| ---------------- | -------------- |
| Deletes old data | Keeps old data |
| Starts fresh     | Adds at end    |
| Overwrites       | Extends        |

---

# 4️⃣ Exclusive Creation Mode (x)

### Purpose

Create a brand-new file.

### Syntax

```python
f = open("new.txt", "x")
```

---

### Result

If file doesn't exist:

✅ Created

If file exists:

❌ FileExistsError

---

## 🖼️ Exclusive Creation

![Image](https://images.openai.com/static-rsc-4/nwx3Lal8MHMP8XHsQwDXJGtYuYA3EPsm_2L429EX6G1A2d1sH5oRsBExVGpL-nJFzHaiuWSE7QyagO-7zqy-P-BzY8_FJMwzasZ6oQIORIHIl29YrDqahHvQjPnh9TQ2ObhqS2MLm1R6Zv8fFztmT0mfyVOMl8HjmuG5wR-eXoYD7gSm9vv7b2HRPi9fn5pp?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/4iUskCJB68eWSRu6OZHIS7l3wMnwPFOA9efsQ7HWmfSrSZOGTvRiy-FalMlIwzosSbBz5qaoSSGoFD179Y3nGO4qJaxQB6XWFebTF73Dv1daIC5f_Mo2ji9a0tDd2JrXQVdWAaZ_4PJwcnHdaZgkYxXo7FkpqSCCb2TyzcrSx1wYNhzRbH2MAVJZs6qmt379?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/_zmXECNB1moz5HTptoaZ8G-mHldMTrs2QWi1nFVeuZBuaIRTsnL4zCzTscpeVpQwRLRch7vXA-zb_BIGQ2TdT408-5W-wAI6VODoV2v5tXIZ_2aPeY_aAa4RmfDkV17lVoGVcTbc0pkkq87QYJeAW9g-MSVKsCPgo0pZY649GOBqu8Fggw8PWGg4-FPTq6qI?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/RGXWUSuLDuzDcClMy1e5VqLioxH13JFYgpmkuk54Z1qfTPs4xkTHGfehHoPHxYGdqWlCgK-ayPEfvqSdpF_Ynd2IjoXeh92H3ZdRfakVXQWIhdU2JCZjGMUNp3WbEKQOhDiCqwGYw1Rh1G7go8DP6iTDtd0LGxGGpdAFaqJka5TQFwJeZLvhYtt5ZvBIxgDr?purpose=fullsize)

---

# 5️⃣ Binary Mode (b)

Used for non-text files.

Examples:

* Images
* Videos
* Audio
* Executables

---

### Example

```python
f = open("photo.png", "rb")
```

---

## 🖼️ Binary Files

![Image](https://images.openai.com/static-rsc-4/HB6g0GEyPfZn6l1JJfzLE-7jwqFGBiyPLxwGGzIAEB-VacRi6W0HaXTpEnNGkDhm415PrGPy-u96NI0Wwz1_1yg1JU8XntA5r5WErOM3cb2aJoCOjVrvHXBFxICdcCSMC0MsI95Hf9n9klF2EBBBzKMYo-oB2G8AK-KucXBn0U58JnRB_-ImROHaEliWx76b?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/pVV90YFEwVSZaKvRaZns5_JYcDowAopD10siWOK2dBd0gAsOehkir1epUetg9aWnE7JU1oi2tD_y4OXpR-j89XqHcB6vojYiz-IXabJS5UrNOyfKX-QdLS8gwr2G5rlo1ISMH5zsljo49d8Wo7kOcwNaR-aBBV-2ysM8Al3Luz1uS7j_ioT99RGShdPC1PVP?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/xxKqD9eiOLF8a9vlMa50FCRBtarLNgSd8fGmyNwD_dp3hw7SK0vTBnWQLc9ufCCsLhkGfSRN2_dZreD8E0jsrKD03-u86zfI_AqX-9MOOKee_IeYm7DyYrlW6pyL6cqyheMCzhTqa5-AwgP9LR8M_Nj0_76hIUuSBxflnyXS8gZ-sbzdzEae5VipHIXyRAXj?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/wDtX3DYH1EQQS5v7ZqOLf1OFHlaIUwR0K50EyBDetEJEYfQ49dU2BufZcSrNG_iJcKcABRXB0VXhY70h9-xU8nwDPwFXtyTDruvMu_PNeV2RBsWlFr6q8QQ68ps4n1vmWQTCQA-Q1YAjvn3LGI9-B5hgoYqm2Pz3XuQ5GkzyfefhUaL7JC9Yd-dx-BQuubPW?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/UJ69AXJYrevObZkmzdVoGzSau55VuTKY9QIdpMgPOdtrc1TAB8V92OQjORcfGzs2zaoJaXf7YspakJbkf76EdAf3WfCV9uhjcepic7oAHFcegiEA7-Pr5d18NeIdZv8O5a1BE9oWGv05migQWtYEQExqmYyNTEue_i7RBdE9Vpp7DD2Sdhb-lTQ_S6MMVz4u?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/O-Ez3DTY1Bs1opJhAGEp4IXT4Y52GG_UTmxHKA89JcoIVGPUjpXX_r0EK-sOHGxyeDMAyvV2HpzTcEOxseq6SIlW78BYju5gV-_jHQBEbRvd7jDA6RUfdDi1Q80y6eNtCAS3Rc0MPgN3oAXeB6mt9zCI5Y0lPSAncEJExIbm5aMBjm0L6jE20lBlgqwPRaqZ?purpose=fullsize)

### Common Binary Modes

| Mode | Meaning       |
| ---- | ------------- |
| rb   | Read Binary   |
| wb   | Write Binary  |
| ab   | Append Binary |

---

# 6️⃣ Plus Mode (+)

Used when reading and writing together.

### Examples

```python
r+
w+
a+
```

---

### Example

```python
f = open("data.txt", "r+")
```

Now you can:

```python
f.read()
f.write("Hello")
```

---

## 🖼️ Read + Write Together

![Image](https://images.openai.com/static-rsc-4/spTOAuDTcQyo0VhDA42aYpNzj3BtGaDglqtGvfmi-79aK-wjIbpOwkWkwZebjm1i-ILKCe9GEmydpIv5wH7KLwLQSQOQdmIGWncrc1K8NAfw0ofJhUPSUNnleE8I4VluB3YFu8gkMpbRM4PFYngKmpHxPop6uLCkD5jEYnLCOaDGiLKfIBsafemk2RakkhCI?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/c5h7OE4Wqelhs2kM1i0PeYVRUU4CnW1OPdtE_5ULFddQVqd8-ZS9Xr5RJGaGImyuTNKKhJWTv5O_vNFJ8HLsFTMO9dukFz3XMIs01QnhFDizMaJ-AtLD_bACgLghDZ0u3ienJvDvBy5rxqF528TScam4SNY0WCANh-olxLL-WeKUw9NfUAKiq8YEdFuJPvL1?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/jA4aio9zZJfOCOz-FkKVASTguZAAKuTj0KrO142VwypZpaq8v4IyLbjyrNrXc8UxdUk9GMTJtGPFwdHWzDP0DL6ncjMHjf54hfs8LYrv_kvOMB43F7Xxlu3zgYAbpHfP8Js_gvWpY8IeFHKX9SE-HHc1DcXqLfB79cDaFkxZT3Nzv3LRgbROgig4wAlz7tUQ?purpose=fullsize)

```text
Read ← File → Write
```

---

# 📊 Complete Mode Summary

| Mode | Purpose      | Creates File | Deletes Data    |
| ---- | ------------ | ------------ | --------------- |
| r    | Read         | ❌ No         | ❌ No            |
| w    | Write        | ✅ Yes        | ✅ Yes           |
| a    | Append       | ✅ Yes        | ❌ No            |
| x    | Create       | ✅ Yes        | Error if exists |
| rb   | Read Binary  | ❌ No         | ❌ No            |
| wb   | Write Binary | ✅ Yes        | ✅ Yes           |
| r+   | Read + Write | ❌ No         | ❌ No            |

---

# 🎯 Interview Questions

### Q1. What is File Handling?

**Answer:**
File handling is the process of storing, reading, writing, and managing data in files.

---

### Q2. Why is RAM not used for permanent storage?

**Answer:**
RAM is volatile memory. Data is lost when power is turned off.

---

### Q3. Difference between Write and Append?

| Write             | Append         |
| ----------------- | -------------- |
| Removes old data  | Keeps old data |
| Writes from start | Writes at end  |

---

### Q4. Which mode creates a new file only?

**Answer:** `x`

---

### Q5. Which mode is used for images?

**Answer:** `rb` (Read Binary)

---

# 🧠 Quick Revision Diagram

```text
File Handling
│
├── Open
│
├── Read (r)
│
├── Write (w)
│
├── Append (a)
│
├── Create (x)
│
├── Binary (b)
│
├── Read+Write (+)
│
└── Close
```

## 🚀 Final Conclusion

File Handling allows Python programs to store data permanently.

### Golden Rule

```text
OPEN
  ↓
READ / WRITE
  ↓
CLOSE
```

Remember:

```python
r  → Read
w  → Write
a  → Append
x  → Create
b  → Binary
+  → Read & Write
```

These are the most important file modes asked in interviews and used in real-world Python projects.
