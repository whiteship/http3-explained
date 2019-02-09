<!--
# Earlier data

QUIC offers both 0-RTT and 1-RTT handshakes that reduce the time it takes to
negotiate and setup a new connection. Compare with the 3-way handshake of TCP.

In addition to that, QUIC offers "early data" support from the get go which is
done to allow more data and it is used more easily than TCP Fast Open.

With the stream concept, another logical connection to the same host can be
done at once without having to wait for the existing one to end first.
-->

# 더 이른 데이터

QUIC은 0-RTT, 1-RTT 핸드쉐이크 둘 다 제공하는데 이는 새로운 연결을 협상하고 설정하는데
걸리는 시간을 줄여준다. TCP의 3웨이 핸드쉐이크와 비교해보라.

또한, QUIC은 더 많은 데이터를 허용하는 "이른 데이터(early data)"를
처음부터 지원하고 이는 TCP Fast Open보다 더 쉽게 사용할 수 있다.

스트림 개념을 사용해서 기존에 있던 연결이 끝나기를 먼저 기다릴 필요 없이 같은 호스트로의
또 다른 논리 연결도 동시에 처리할 수 있다.

<!--
## TCP Fast Open is problematic

TCP Fast Open was published as [RFC 7413](https://tools.ietf.org/html/rfc7413)
in December 2014 and that specification describes how applications can pass
data to the server to be delivered already in the first TCP SYN packet.

Actual support for this feature in the wild has taken time and is riddled with
problems even today in 2018. The TCP stack implementors have had issues and so
have applications trying to take advantage of this feature - both in knowing
in which OS version to try to activate it but also in figuring out how to
gracefully back down and deal when problems arise. Several networks have been
identified to interfere with TFO traffic and they have thus actively ruined
such TCP handshakes.
-->

## 문제가 있는 TCP Fast Open

TCP Fast Open는 2014년 12월 [RFC 7413](https://tools.ietf.org/html/rfc7413)로
발행되었고 이 명세는 이미 전달된 첫 번째 TCP SYN 패킷에 있던 데이터를 어떻게 서버로 보낼 수 있는지 설명한다.

이 기능을 실제로 지원하기까지 시간이 꽤 걸렸고 2018년인 오늘날까지도 문제로 가득하다. TCP 스택을
구현하는 사람들 뿐 아니라 이 기능으로 이점을 취하려는 애플리케이션도 이슈를 겪어왔다. 둘 모두 이를 
활성화하기 위해 OS 버전뿐만 아니라 문제가 발생하면 그레이스풀하게 철회하고 문제를 다루는 방법도 알고 
있다. 몇몇 네트워크가 TFO 트래픽을 방해하는 것으로 밝혀졌고 이러한 TCP 핸드쉐이크를 적극적으로 망쳐왔다.
