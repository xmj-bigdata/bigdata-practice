## 镜像源切换
https://blog.csdn.net/wdy_2099/article/details/70578529

    mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
    cd /etc/yum.repos.d/
    wget http://mirrors.163.com/.help/CentOS7-Base-163.repo
    mv CentOS7-Base-163.repo CentOS-Base.repo
    yum clean all
    yum makecache
## 问题
配置账号密码后，重启项目即可

    #修改配置文件
    sudo vi /etc/gitlab/gitlab.rb
    
    #邮件配置
    gitlab_rails['smtp_enable'] = true
    gitlab_rails['smtp_address'] = 'smtp.163.com'
    gitlab_rails['smtp_port'] = 465
    gitlab_rails['smtp_user_name'] = 'yourmail@163.com'
    gitlab_rails['smtp_password'] = 'yourpasswd'
    gitlab_rails['smtp_domain'] = 'smtp.163.com'
    gitlab_rails['smtp_authentication'] = 'login'
    gitlab_rails['smtp_enable_starttls_auto'] = true
    gitlab_rails['smtp_tls'] = true
    gitlab_rails['gitlab_email_enabled'] = true
    gitlab_rails['gitlab_email_from'] = 'yourmail@163.com'
    gitlab_rails['gitlab_email_display_name'] = 'Gitlab'

#保存后，重新配置并启动GitLab
sudo gitlab-ctl reconfigure


## setting account
root/root@1023

https://ken.io/note/centos7-gitlab-install-tutorial

https://blog.csdn.net/littlebrain4solving/article/details/80168493