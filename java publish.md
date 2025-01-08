发布jar包到maven中央仓库
1. Sonatype(https://central.sonatype.com) 注册
2. Add Namespace io.github.yiyicity
3. Verify Namespace,根据提示在github上创建库进行验证。
4. 点右上角的 View Account， Generate User Token，生成结果如下：

<server>
	<id>${server}</id>
	<username>rdSysmmd</username>
	<password>adffffffffNNMLaMMaNMi</password>
</server
${server} 改成 yiyicity
<server>
	<id>yiyicity</id>
	<username>rdSysmmd</username>
	<password>adffffffffNNMLaMMaNMi</password>
</server
拷贝到maven的conf/settings.xml
5.进入GPG(https://gnupg.org/download/index.html)   -> GnuPG binary releases -> Gpg4win ->下载 -> 默认安装 -> 进入C:\Program Files (x86)\GnuPG\bin->cmd->输入命令
6. gpg --gen-key   依次输入名称，邮箱地址，名称直接用上面的yiyicity
   生成结果如下：
   pub   ed25519 2025-01-07 [SC] [expires: 2028-01-07]
      D5B6594MM416AE5C4BD9A7722484D69C1D35DD52
uid                      yiyicity <www.yiyi.city@gmail.com>
sub   cv25519 2025-01-07 [E] [expires: 2028-01-07]

7. 发布密钥
gpg --keyserver keys.openpgp.org --send-keys D5B6594MM416AE5C4BD9A7722484D69C1D35DD52

可选发布地址：keyserver.ubuntu.com，pgp.mit.edu
8. 验证秘钥
gpg --keyserver keys.openpgp.org --recv-keys D5B6594MM416AE5C4BD9A7722484D69C1D35DD52
基本提示如下标识成功：
gpg: key SDMMMDIXXSEA
gpg: Total number processed: 1
9. 发布JAR包，pom参考 
