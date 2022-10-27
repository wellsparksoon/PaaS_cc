在PaaS上部署Xc,带伪装页面



# 配置

vlss + vmss + trjan + shdscks2022

- 地址：**x.x.x.x**（由服务平台提供）
- 端口：**4-4-3**（通常自带TLS）
- 用户ID/密码：**1eb6e917774b4a84aff6b058577c60a5**（默认）
- 传输协议：**w-s**
- 传输层安全：**t-l-s**
- 加密
  - shadowsocks：**2022-blake3-aes-128-gcm**
- 路径（默认）
  - vlss：**/vlss/1eb6e917774b4a84aff6b058577c60a5**
  - vmss：**/vmss/1eb6e917774b4a84aff6b058577c60a5**
  - trjan：**/trojan/1eb6e917774b4a84aff6b058577c60a5**
  - shadscks：**/shdscks/1eb6e917774b4a84aff6b058577c60a5**

> 其他参数默认

****



# 环境变量

| 变量名           | 默认值                           | 描述            |
| ---------------- | -------------------------------- | --------------- |
| PORT             | 8080                             | 端口            |
| UUID             | 1eb6e917774b4a84aff6b058577c60a5 | 用户ID/密码     |
| PATH_vlss       | /vlss/$UUID                     | vless路径       |
| PATH_vmss       | /vmss/$UUID                     | vmess路径       |
| PATH_trjan      | /trjan/$UUID                    | trojan路径      |
| PATH_shdscks | /shdscks/$UUID               | shadowsocks路径 |

为兼容**shdscks2022**，生成的UUID需去除所有`-`

> 例：*1eb6e917-774b-4a84-aff6-b058577c60a5* => *1eb6e917774b4a84aff6b058577c60a5*
> 
> 虽然配置的*UUID*里去除了`-`，但是<u>**vmss/vlss**</u>可以使用带`-`的<u>1eb6e917-774b-4a84-aff6-b058577c60a5</u>作为*用户ID*（针对SagNet连不上的情况）

默认路径：**/协议名称/设置的UUID**

1. 假设UUID为：0123456789
2. 则vlss默认的路径为：/vlss/0123456789

> 如果设置vlss路径为<u>/vlss1</u>，则配置路径就为<u>/vlss1</u>

****



[Xcv1.6.0](https://github.com/XTLS/Xc-core)	·	[Caddy v2.6.1](https://github.com/caddyserver/caddy)	
