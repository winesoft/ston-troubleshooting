.. _install:

설치
******************

STON Edge Server를 설치하는 과정에서 발생할 수 있는 오류에 대한 트러블슈팅을 안내한다.

.. toctree::
   :maxdepth: 2


.. _install-uncompress:

패키지 압축 해제 불가
====================================

STON Edge Server 바이너리 패키지 압축 해제가 실패한다. ::

   $ tar -zxf ston.19.05.0.rhel.2.6.32.x64.tar.gz

-  원인: root 권한이 없다.
   대처: root 권한을 생성하거나, 슈퍼유저 권한으로 접속한다 ($ sudo su)


.. _install-welcomepage:

웰컴 페이지 로딩 실패
==========================

설치 후 STON Edge Server 웰컴 페이지가 로딩되지 않는다

-  원인: 

.. _install-WM:

웹매니지먼트 페이지 로딩 실패
==========================

설치 후 STON Edge Server 웰컴 페이지가 표시되나, 웹매니지먼트 페이지는 나오지 않는다

-  원인 #1: 아파치가 설치되지 않았다 (httpd)
   대처: yum install httpd
   
-  원인 #2: WM 구동에 필요한 패키지들이 구버전이다 
   대처: 신 버전으로 링크를 바꿔준다 ::
   
   $ ln -Tfs /lib64/libapr-1.so.0.6.3 ./libapr-1.so
   $ ln -Tfs /lib64/libapr-1.so.0.6.3 ./libapr-1.so.0
   $ ln -Tfs /lib64/libaprutil-1.so.0.6.1 ./libaprutil-1.so
   $ ln -Tfs /lib64/libaprutil-1.so.0.6.1 ./libaprutil-1.so.0
   $ ./wm.sh start


팁
******************

.. _install-license:

라이선스 파일 복사
====================================

발급된 라이선스 파일의 내용을 텍스트로 긁어서 vi로 붙여넣을수 있다. ::

      $ vi /usr/local/ston/license.xml
      :wq
