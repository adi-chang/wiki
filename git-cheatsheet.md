# git cheatsheet

download git dari : https://git-scm.com/downloads

dari source: [git-scm.com](https://git-scm.com/)

disebutkan bahwa : 

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

berikut ini beberapa informasi perintah yang sering digunakan saat kita menggunakan git 

### set user dan email git 

`git config --global user.name "your_user_name"`
`git config --global user.email "your_email@domain.com"`

### Cek git setting

`git config --list`

- untuk melihat info user
`git config user.name` 
- untuk melihat info email
`git config user.email`

### set default editor

misal ingin menggunakan vs code sebagai default editor 
`git config --global core.editor "code --wait"`

### memasang ssh key ke git lokal

#### generating a new ssh key

`ssh-keygen -t rsa -b 4096 -C "youremailaccount@youremaildomain.com"`

perintah di atas akan melakukan proses create a new ssh key
> Generating public/private rsa key pair.

> Enter a file in which to save the key (/c/Users/you/.ssh/id_rsa):[Press enter]

press enter untuk save key ke default location

> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]

jika ingin menggunakan password. ketik password yang akan digunakan.

#### cek ssh key ?

checknya ke folder .ssh under user home folder (ex. on windows: c:/users/<user_name>/.ssh)
akan ada file id_rsa id_rsa.pub 

kemudian anda harus mengaktifkan service ssh-agent

#### check ssh-agent via windows terminal [untuk os windows]

`get-service ssh-agent`
`get-service ssh-agent | select starttype`
`set-service ssh-agent -startuptype manual (under administrator user account)`
`start-service ssh-agent`

cara paling gampang nge-run ssh-agent
```open services.msc > cari OpenSSH Authentication Agent > Start Service nya```
 
kemudian add ssh key yang terbentuk ke account github anda

### untuk melakukan clone github repository ke local git

git clone <url_addr>

#### using ssh

`git clone <ssh_address>`

contoh: ```git clone git@github.com:adi-chang/hello-world.git```

#### using http

`git clone <https_address>`

contoh : ```git clone https://github.com/OmGigitOm/git-cheatsheet.git```

### untuk melihat origin dari remote github repo 

`git remote -v`

### untuk mengupdate repo local terhadap perubahan yang ada pada repo github (utama)

`git pull origin master (pull data terbaru dari github ke branch master)`

```git pull (pull data terbaru dari github ke branch aktif)```

### untuk melihat branch yang ada 

`git branch`

### untuk membuat branch baru

`git branch <nama-branch-baru>`

### untuk pindaah ke branch yang sudah ada 

`git checkout <nama_branch_target>`

### untuk membuat branch baru sekaligus pindah ke branch baru tersebut

`git checkout -b <nama-branch-baru>`

### untuk menampilkan working tree status (aktif di branch apa, perubahan-perubahan yang terjadi apa saja)

`git status`

### untuk menampilkan informasi history commit yang sudah terjadi 

`git log`

### untuk menambahkan file - file ke index untuk di commit

```git add <nama-file>``` [untuk menambahkan file satu per satu]

```git add .``` [untuk menambahkan seluruh perubahan]

### untuk me-record perubahan ke repository

```git commit [-m "message"]```

#### untuk push PR ke branch master

```git push -u origin HEAD```

### untuk merge branch master ke branch lain (agar apa yang ada di master terupdate ke branch tersebut)

`git checkout <nama-branch>`

kemudian

`git merge master`






































