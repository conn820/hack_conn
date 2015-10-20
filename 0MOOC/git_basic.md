Git使用基本方法
---

### 1.创建仓库
案例：创建一个名为test的仓库在本地

```
$ mkdir test #创建了一个名为test的仓库
$ cd test #进入这个仓库中
$ pwd #显示当前目录
$ git init #命令把这个目录变成git可以管理的仓库

```


### 2. 把文件添加到仓库中
案例：将conn.md添加到test.git仓库中

- Step1：把文件放到这个仓库中
- Step2：向Git声明自己添加了文件
	`$ git add conn.md`
- Step3：确认这个改动
	`$ git commit -m "blablabla"`

### 3. 把本地文件推送到github中

- `git remote add origin git@server-name:path/repo-name.git`；
- `git push -u origin master`第一次推送master分支的所有内容；
- `git push origin master`推送最新修改；


### 4. 把远程文件clone到本地
`$ git clone git@github.com:michaelliao/gitskills.git`