# Heimdallr

用于被动式的嗅探相关高危指纹和蜜罐特征，并进行告警的谷歌插件

## 使用须知

1、插件的识别对象基于【域名+端口】或【IP+端口】，对于同一web服务下通过路由分发的不同业务系统不做进一步区分

2、插件默认只开启被动流量监控，不会因为敏感指纹的探测触发防火墙封禁

3、插件目的为发现直接访问无法识别的组件或框架，请勿添加可以直接识别的组件的特征到指纹库（如spark未授权页面），增加无意义的识别调用。

4、部分页面告警请求体数据为json格式、请求头Content-Type为application/json格式时，不一定是当前document的请求，有可能是当前document页加载的相关页面的接口请求满足条件

5、因为谷歌的安全限制和chrome内核的历史遗留问题，插件对响应内容的检查与其他指纹位置的检查不同，浏览器页面顶部会出现调试提示，可通过插件设置关闭响应包检查功能或添加谷歌浏览器的启动项规避提示。

6、插件不缓存功能开启后，页面响应不会被缓存，可能会稍微增加流量和内存使用

7、介于编码问题，响应体指纹仅使用ascii编码范围内的字符的规则可靠，中文或其他字符可能因编码不同出现无法匹配规则的情况，待后续改进。

## TODO

1、跳转前后首次请求扫描结果丢失问题

2、对响应体检测前进行筛选

2、插件级别的暂停功能

3、主动扫描部分指纹

4、UA、Cookie自定义

4、机器码伪装

6、联合规则检测

7、嵌入Wappalyzer

## 致谢

https://github.com/iiiusky/AntiHoneypot-Chrome-simple

https://github.com/cnrstar/anti-honeypot

https://github.com/Monyer/antiHoneyPot
