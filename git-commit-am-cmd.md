# 🔧 Understanding `git commit -am`

Learn how to efficiently commit changes using Git’s `-am` flag.

---

## 🛠️ Breakdown Example

```bash
echo "hello" > a.txt
git add a.txt
git commit -m "added a.txt"

# Now make changes to a.txt
echo "new line" >> a.txt

# Instead of git add + git commit
git commit -am "updated a.txt"
```

✅ No need to run `git add` again — the `-a` flag automatically stages **modified tracked files**.

---

## ⚠️ Important Warning

❌ `git commit -am` **does NOT include new/untracked files**

Only files that were **already added/tracked** by Git will be included in the commit.

### ❌ Example (Will NOT work):

```bash
echo "new" > newfile.txt
git commit -am "add newfile"   # ❌ Will not work!
```

🚫 Why? Because `newfile.txt` was never staged using `git add`.

---

### ✅ Correct Way to Commit New Files:

```bash
git add newfile.txt
git commit -m "add newfile"
```

---

## ✅ Summary

| Command                         | What It Does                                              |
| ------------------------------- | --------------------------------------------------------- |
| `git commit -m "msg"`           | Commits only **already staged files**                     |
| `git commit -am "msg"`          | Automatically **stages + commits modified tracked files** |
| `git add file && git commit -m` | Required for **new/untracked files**                      |

---

🧐 **Pro Tip:** Run `git status` before committing to check which files are tracked vs untracked.






