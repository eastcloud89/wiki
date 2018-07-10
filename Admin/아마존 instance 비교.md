# 아마존 instance 비교
## (m)3 vs (m)4
* (m)3 - ssd(local storage)사용, 휘발성(인스턴스 중지 또는 종료 되었을 때 데이터 날라감), ebs에 비해 훨씬 빠름
* (m)4 - ebs 사용, $0.123 -> 88560 + ebs요금
* 

R4.large가 가장 효율적!

[참고](https://www.ec2instances.info/?region=ap-northeast-2)