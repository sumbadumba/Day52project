# Day52project

윈도우에는 창이 두가지 종류가있다.
모달-> 창 / 다음 라인 진행 x
모달리스-> 창 / 다음 라인진행 o 


숙제1:
xml 파일을 읽어들여 화면에 출력하는 프로그램을 만드시오 
	- 파일 선택창으로 XML을 선택
	- 출력 길이가 길어지면 스크롤 (키보드나 마우스로)
	- 수업시간에 사용한 sprite를 사용해도 됨



	node = root->FirstChildElement()->FirstChildElement();

	ws = L"\n게시판\n\n";

	ws += L"No\t제목\t글쓴이\t만든날짜\t만든시각\t조회수\t좋아요\t \n";

	while(1)
	{
		// No.
		ws += String::ToWString(node->GetText());
		ws += L"\t";

		// 제목
		node = node->NextSiblingElement();
		ws += String::ToWString(node->GetText());
		ws += L"\t";

		// 글쓴이
		node = node->NextSiblingElement();
		ws += String::ToWString(node->GetText());
		ws += L"\t";

		// 만든 날짜
		node = node->NextSiblingElement();
		ws += String::ToWString(node->GetText());
		ws += L"\t";

		// 만든 시각
		node = node->NextSiblingElement();
		ws += String::ToWString(node->GetText());
		ws += L"\t";

		// 조회수
		node = node->NextSiblingElement();
		ws += String::ToWString(node->GetText());
		ws += L"\t";

		// 좋아요
		node = node->NextSiblingElement();
		ws += String::ToWString(node->GetText());
		ws += L"\t\n";

		// NextSiblingElement 
		if (node->Parent()->NextSiblingElement() != 0)
			node = node->Parent()->NextSiblingElement()->FirstChildElement();
		else
			break;
	}
	
