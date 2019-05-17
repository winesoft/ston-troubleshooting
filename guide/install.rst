.. _install:

설치
******************

이 장에서는 STON Edge Server를 설치하는 과정에서 발생할 수 있는 오류에 대한 트러블슈팅을 안내한다.

.. toctree::
   :maxdepth: 2


.. _install-uncompress:

패키지 압축 해제 불가
====================================

STON Edge Server 바이너리 패키지 압축 해제가 실패한다. ::

   $ tar -zxf ston.19.05.0.rhel.2.6.32.x64.tar.gz

-  root 권한이 없다.
   sudo su


.. _install-license:

라이선스 파일 복사
====================================

발급된 라이선스 파일의 내용을 텍스트로 긁어서 vi로 붙여넣을수 있다. ::

      $ vi /usr/local/ston/license.xml
      :wq
