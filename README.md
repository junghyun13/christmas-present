# christmas-present
# python
첫 번째 줄에서는 아이들과 거점지를 방문한 횟수 n이 주어진다.다음 n줄에는 array가 있고 그 다음 a개의 숫자가 들어온다. 이는 거점지에서 array개의 선물을 충전하는 것이고, 그 숫자들이 선물의 가치. 만약 array가 0이면 아이들을 만남. 0 아니면 거점지을 방문하며 선물을 충전해 나가고 아이들을 만날 때마다 가지고 있는 가장 가치가 큰 선물 하나를 선물해 줄 것이다. 아이들에게 준 선물의 가치를 출력하시오. 만약 줄 선물이 없다면 -1을 출력하는 프로그램을 작성해보자!


import heapq #우선순위 큐 (낮은값부터 저장)
n=int(input()) #방문지 
present=[]
for i in range(n):
  array=list(map(int,input().split()))
  if array[0]==0: #거점지에 도착하지 않음 
    if len(present)==0:
      print(-1)
    else: #가지고 있는 가장 큰 가치선물을 먼저 준다
      give=-heapq.heappop(present) #꺼낼때 -붙이기
      print(give) #큰수가 가장앞에서 먼저 나옴 
  else:
    for j in range(array[0]): #거점지에서 선물 충전 
      heapq.heappush(present,-array[j+1]) #저장은 -붙이기
