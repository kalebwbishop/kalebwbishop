# Generate an SSH Key for GitHub

This will allow you to generate an SSH key for cloning repos on new devices.

## 1. Generate the SSH Key

```bash
ssh-keygen -t rsa -b 4096 -C <email>
```


## 2. Add the SSH Key to the SSH Agent
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

## 3. Copy the SSH Key to Your Clipboard
### Windows
```bash
pbcopy < ~/.ssh/id_rsa.pub
```

### Linux / Mac
```bash
xclip -selection clipboard < ~/.ssh/id_rsa.pub
```

## 4. Add the SSH Key to GitHub
Go to github and add the SSH Key to the profile settings.

## 5. Verify
```bash
ssh -T git@github.com
```