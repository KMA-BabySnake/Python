

	word = ''
	character = '`~!@#$%^&*()_-=+|\\]}[{;:\'",<.>/?' 
	lenght = 0
	bug = 0
	flag = 0
	fl = 0
	f = open("wordlist.txt","r")
	myfile = f.read()# mở và đọc file thoi 

	for x in myfile:# chạy từng kí tự trong 'file'															
		if x == ' ' or x == '\n':# xét xem có phải là khoảng trống hay xuống dòng hay k
			bug += 1		# tăng biến bug và kết hợp cới biến bên dưới để tăng biến đếm chữ trong file lên 	
			for y in character:	# bước này xét xem kí tự trc đó vừa ms đọc xong có phải là lí tự đặt biệt hay k
				for z in word:	# đọc từng kí tự trong chuỗi 'Word ''
					if y == z:	# nếu thuộc kí tự đặt biệt thì tăng biến 'fl'
						fl += 1				
						break # thoát cho khỏi phải đọc nữa 
			if fl == len(word) and fl > 0:# điều kiện để giảm biến đếm xuống ki file có chứa kí tự đựa biệt đứng riêng lẻ hay liên tiếp với nhau
				lenght -= 1					
				fl = 0		# reset biến 'fl' để dùng những lượt sau
			if bug == 1 and len(word) > 0:# điều kiện để tăng biến đếm chữ trong file
				lenght += 1

				word =''	# reset chuỗi 'word' tránh lưu nhìu gây mất tai nguyên
		else:			# đây là trường hợp khi gặp lí tự k phải là khảng trắng hay xuống dòng trong file
			word += x 		# lưu lí tự vào chuỗi để phục vụ mục đích trên
			bug = 0			# reset biến "bug"

	print(lenght+1)
	

