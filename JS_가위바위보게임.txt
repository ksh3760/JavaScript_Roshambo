// 가위바위보 게임
function game() {

	var userInput;				// 사용자 입력
	var comNum;				// 컴퓨터 난수
	var cnt 		= 0;			// 게임 횟수
	var result		= 0;			// 이긴 횟수
	var arrNum 	= ["가위", "바위", "보"];	// 가위바위보를 저장하는 배열
	var flag 		= true;			// 사용자 입력값 판단 (boolean)
	var restart	= true;			// 재시작 (boolean)


	do {	

		// 사용자가 올바른 값을 입력했는지 판단
		do {
			userInput = prompt("가위, 바위, 보 중 하나를 입력하세요.");
		
			if(userInput == "가위" || userInput == "바위" || userInput == "보") {
				flag = false;
			} else {
				alert("경고 : 잘못된 값을 입력 하셨습니다.");
			}
		
		} while(flag)

		comNum = Math.floor(Math.random() * 3)	// 0:가위 1:바위 2:보	
		cnt +=1;
	
		// 사용자 입력 판단
		if(userInput == "가위") {
 		  	 userInput = 0;
		}
		if(userInput == "바위") {
   			 userInput = 1;
		}
		if(userInput == "보") {
   			 userInput = 2;
		}
	
		console.log("사용자 : " + arrNum[userInput] + " 컴퓨터 : " + arrNum[comNum]);
    

		//승패 확인
		if(userInput - comNum == 1 || userInput - comNum == -2 ){
			result += 1;
   			console.log("승리");
		} else
		if(userInput - comNum == -1 || userInput - comNum == 2 ){
   			console.log("패배");
		} else
		if(userInput - comNum == 0){
  			console.log( "무승부");
		}
		
		// 재시작 여부 ( true / false )
		restart = confirm("계속 하시겠습니까?");

	} while(restart);
	
	// 결과 출력
	console.log(cnt + "번 중 " + result + "번 이겼습니다.")

} // end game()
