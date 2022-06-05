1 리눅스 명령어  
#  
  - **top**
  
    - 시스템의 프로세스/메모리 사용 상태를 5초 간격으로 업데이트하여 출력함   
      프로세스의 정보, CPU(사용률), 메모리, 스왑의 상태를 출력함
  
    - 출력 기본값
      - 현재시간   
      - 시스템 업데이트(1) 시간   
      - 시스템에 로그인한 사용자 수   
      - 지난 1분   
      - 지난 5분   
      - 지난 15분 간의 시스템 평균 부하   
  
    - CPU 관련 명령어
      - %us: 유저 레벨에서 사용하고 있는 CPU의 비중
      - %sy: 시스템 레벨에서 사용하고 있는 CPU의 비중
      - %id: 유휴 상태의 CPU의 비중
      - %wa: 시스템이 I/O 요청을 처리하지 못한 상태에서의 CPU idle 상태인 비중
  
    - 옵션
      - -b: batch 모드로 정보를 출력함, 실시간 상화 대화형 모드로 정보를 일렬로 출력함
      - -n num: 지정한 주기(num)만큼 업데이트 정보를 출력함
      - -d delay: 지정한 시간(초)의 간격으로 정보를 업데이트하여 출력함
      - -H: 모든 개별 쓰레드를 보여줌
      - -i idle: 토글값 off 시, idle 프로세스나 좀비 프로세스 정보를 출력하지 않음
      - -p pid: 지정한 프로세스 ID(pid)의 정보만을 출력함
      - -q: 시간의 간격 없이 계속해서 업데이트 정보를 출력함
      - -s: 시큐어 모드로 몇 개의 대화식 명령을 비활성화함
      - -S: cumulative 모드로 누적된 정보를 출력함
  
    - 실행 후 단축키
      - space: 정보를 업데이트함
      - shift+p: CPU 사용률이 높은 순서대로 표시함
      - shift+m: 메모리 사용률이 높은 순서대로 표시함
      - shift+t: 프로세스가 돌아가고 있는 시간 순서대로 표시함
      - k: 프로세스를 종료함
      - a: 메모리 사용량에 따라 정렬함
      - b: Batch 모드
      - c: 명령행, 프로그램 이름 토글
      - h: 도움말
      - n or #: 출력할 프로세스 수를 지정함
      - s: 출력할 정보의 업데이트 시간을 지정함
      - q: top을 종료함
      - u: 지정된 유효 사용자에 의한 프로세스만 보여줌
      - U: 지정된 실제 사용자에 의한 프로세스만 보여줌
      - 1: CPU core별 사용량을 보여줌
  
    - 프로세스  
      ![image](https://user-images.githubusercontent.com/86909494/172041875-87993c0d-d4f0-4719-ab10-d4cc838bfbbb.png)
      - PID: 프로세스 ID
      - USER: 프로세스 사용자명
      - PR: 프로세스의 우선 순위(PRiority)
      - NI: nice 우선 순위 값
      - VIRT: 가상 메모리의 사용량(SWAP+RES)
      - RES: 현재 페이지가 상주하고 있는 크기(REsident Size)
      - SHR: 분할된 페이지, 프로세스에 의해 사용된 메모리를 나눈 메모리의 총합
      - S: 프로세스의 상태
        1. S: 슬립(Sleeping)
        2. R: 실행 가능(Running)
        3. W: 메모리에 상주한 페이지가 없는 프로세스(sWapped out process)
        4. Z: 좀비(Zombies)
      - %CPU: 프로세스가 사용하는 CPU의 사용률
      - %MEM: 프로세스가 사용하는 메모리의 사용률
      - TIME+: 가동 
      - COMMAND: 실행된 명령어  
#  
  - **ps(process status)**  
  
    - 현재 실행 중인 프로세스의 목록과 상태 정보를 보여줌
  
    - ps의 옵션은 전통적인 유닉스(System V, BSD, GNU)에 따라서 결과와 표기법에서 차이가 나타남
  
    - 옵션
      - 전체 프로세스와 관련된 옵션
        1. -A: 모든 프로세스를 출력함
        2. -N or --deselect: ps 프로세스를 제외하고 출력함
        3. -a: 세션 리더 및 터미널에 속하지 않는 프로세스를 제외하고 출력함
        4. -d: 세션 리더를 제외한 모든 프로세스를 출력함
        5. -e: 커널 프로세스를 제외한 모든 프로세스를 출력함
        6. T: 현재 터미널의 모든 프로세스를 출력함
        7. a: 현재 터미널의 사용자 고유 프로세스를 출력함
        8. r: 현재 실행 중인 프로세스를 출력함
        9. x: 터미널이 없는 프로세스를 출력함
      - 특정 프로세스를 선택하여 보여주는 옵션
        1. -C: 지정한 명령어 이름에 관련된 정보를 출력함
        2. -p/p,--pid ID(ID): 프로세스 ID를 출력/지정함
        3. -s, --sid: 세션 ID를 지정함
        4. t, -t: tty를 지정함
        5. --tty: 터미널을 지정함
        6. -U/--User : 실제 사용자 이름이나 ID를 출력/지정함
        7. U/-u/--user : 유효 사용자 이름이나 ID를 지정함
        8. -G/--Group: 그룹 ID에 관련된 정보를 출력(이름 지원)/지정함
        9. -g/--group : 지정한 세션 리더 혹은 그룹명에 관련한 정보를 출력/지정함
      - 자주 사용되는 옵션
        1. aux: 실행 중인 모든 프로세스를 확인함  
           auxf: 실행 중인 프로세스를 트리 구조로 출력함  
           auxfww: 실행 중인 프로세스를 트리 구조와 모든 실행 중인 옵션으로 확인함
        2. -ef: PID와 PPID 등을 확인함  
           ef | grep '프로세스명': '프로세스명'의 프로세스 구동을 확인함
  
    - 필드  
      ![image](https://user-images.githubusercontent.com/86909494/172041916-6f447541-11f5-4bd4-85d6-2335352595d8.png)

      - F: 프로세스 플래그
      - S: 프로세스의 현재 상태
      - USER/UID: 프로세스 소유자의 이름(BSD/SYSTEM V)
      - PID: 프로세스 식별자
      - PPID: 부모 프로세스 식별자
      - C: CPU 사용량
      - PRI: 프로세스 우선 순위
      - NI: 프로세스의 CPU 자원 사용 우선 순위(Nice)
      - ADDR: 프로세스의 메모리 주소
      - SZ: 가상 메모리 사용량
      - STIME: 프로세스 시작 시간
      - TTY: 프로세스가 실행된 터미널의 종류와 번호
      - TIME: 총 CPU 사용시간
      - CMD: 프로세스 수행 명령어  
#  
  - **jobs**
  
    - 현재 세션의 작업 상태를 출력함
  
    - 사용
      - jobs [옵션] [jobID]
      - jobs -x command [args]
  
    - 옵션
      - -l: 프로세스 그룹 ID를 state 피드 앞에 출력함
      - -n: 프로세스 그룹 중에 대표 프로세스 ID를 출력함
      - -p: 각 프로세스 ID에 대해 한 행씩 출력함
      - command: 지정한 명령어를 실행함
  
    - 상태값
      - Running: 작업이 일시중단되지 않았고, 종료하지않고 진행 중임
      - Done: 작업이 완료되어 0을 반환하고 종료함
      - Done (code): 작업이 정상적으로 완료, 0이 아닌 코드를 반환했음
      - Stopped: 작업이 일시중단됨
        || 설명 |
        | :-------: | --------------------------------- |
        | (SIGTSTP) | SIGTSTP 신호가 작업을 일시 중단했음 |  
        | (SIGSTOP) | SIGSTOP 신호가 작업을 일시 중단했음 |  
        | (SIGTTIN) | SIGTTIN 신호가 작업을 일시 중단했음 |  
        | (SIGTTOU) | SIGTTOU 신호가 작업을 일시 중단했음 |  
#  
  - **kill**
  
    - 프로세스를 종료함
  
    - 사용
      - kill [-s시그널] [-a] pid...
      - kill -l [시그널]
  
    - 옵션
      - pid...: 종료시킬 프로세스 ID나 프로세스 이름을 지정함
      - -s: 전달할 시그널의 종류(시그널 이름/번호)를 지정함
      - -l: 시그널로 사용할 수 있는 시그널 이름들을 나타냄
      - -1,: -HUP 프로세스를 재활성화함
      - -9: 프로세스를 강제로 종료시킴
      - -HUP pid: 프로세스 종료 후 다시 재실행함
  
    - 필드
      - PID: 프로세스 ID
      - %CPU: 프로세스가 사용하는 CPU의 사용률
      - %MEM: 프로세스가 사용하는 메모리의 사용률
      - VSZ: 가상 메모리에 있는 프로세스의 크기
      - RSS: 프로세스의 실제 메모리 크기
      - TTY: 연결되어 있는 터미널
      - STAT: 실행되고 있는 프로세스 상태
      - START: 프로세스가 시작된 날짜
      - TIME: 프로세스가 소비한 총 시간
      - COMMAND: 실행된 명령어  
#  
#  
2 vim 에디터 매크로 사용방법
  
  - 기본
    - (커맨드 모드에서)q와 a를 눌러 a키에 매크로를 recording함
    - 매크로로 반복하려는 작업을 입력함
    - (커맨드 모드에서)q를 눌러 recording을 종료함
    - @
      1. @a: 1회 실행함
      2. @@: 방금 실행한 매크로를 실행함 
      3. n@a: 매크로를 n회 실행함
  
  - 자주 사용하는 매크로 등록
    - ~/.vimrc 파일을 염
    - 등록
      1. let @[매크로명]='을 입력하고, Ctrl+r, Ctrl+r, 만들었던 매크로키를 누르고 사용한 매크로 내용이 출력되면 마지막으로 '입력
      2. let @[매크로명]='매크로 작업 문자열' 을 입력
    - 사용 시에 커맨드 모드에서 "매크로명p를 입력하여 레지스터로부터 바로 붙여넣기함  
  
#  
**20213076 김윤아**
