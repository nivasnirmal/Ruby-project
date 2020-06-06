# Ruby-project
 require 'csv'
def soccer
	puts ""
	puts "------------------ Soccer selection -----------------------"
	puts ""
	puts "Weight(measured in pounds)"
    w = gets.to_i
    puts "Height(measured in inches)"
    h = gets.to_i
    bmi=(w * 703)/(h*h)
    puts "The BMI is:#{bmi}"    
    if bmi == 30
        puts "you are perfect"
    elsif bmi >= 20
        puts "Eligible"
    else
        puts" Not eligible"
    end
end
def basketball
	puts ""
	puts "------------------ BASKET BALL SELECTION -----------------------"
	puts ""
	puts "Weight(measured in pounds)"
    w = gets.to_i
    puts "Height(measured in inches)"
    h = gets.to_i
    bmi=(w * 703)/(h*h)
    puts "The BMI is:#{bmi}"    
    if bmi == 30
        puts "you are perfect"
    elsif bmi >= 20
        puts "Eligible"
    else
        puts" Not eligible"
    end
	
end
def volleyball
	puts ""
	puts "------------------ VOLLEY BALL SELECTION -----------------------"
	puts ""
	puts "Weight(measured in pounds)"
    w = gets.to_i
    puts "Height(measured in inches)"
    h = gets.to_i
    bmi=(w * 703)/(h*h)
    puts "The BMI is:#{bmi}"    
    if bmi == 30
        puts "you are perfect"
    elsif bmi >= 20
        puts "Eligible"
    else
        puts" Not eligible"
    end
	
end
def baseball
	puts ""
	puts "------------------ BASE BALL SELECTION  -----------------------"
	puts ""
	puts "Weight(measured in pounds)"
    w = gets.to_i
    puts "Height(measured in inches)"
    h = gets.to_i
    bmi=(w * 703)/(h*h)
    puts "The BMI is:#{bmi}"    
    if bmi == 30
        puts "you are perfect"
    elsif bmi >= 20
        puts "Eligible"
    else
        puts" Not eligible"
    end
	
end
def shuttle
	puts ""
	puts "------------------ SHUTTLE SELECTION  -----------------------"
	puts ""
	puts "Weight(measured in pounds)"
    w = gets.to_i
    puts "Height(measured in inches)"
    h = gets.to_i
    bmi=(w * 703)/(h*h)
    puts "The BMI is:#{bmi}"    
    if bmi == 30
        puts "you are perfect"
    elsif bmi >= 26
        puts "Eligible"
    else
        puts" Not eligible"
    end
	
end
def adlogin()
	puts "Enter the username"
	usr = gets.chomp
	puts "Enter the password"
	pass = gets.chomp
	if(usr=="test" and pass=="test12")
	    puts ""
		puts "Login Sucessfull..!!"
		puts ""
		puts ""
		puts "1. For Add new data"
		puts "2. For updating new data"
		puts "Enter the choice"
		ch2 = gets.to_i
		case ch2
		when 1
			adddata()
		when 2
			upatedata()
		else
			puts "Invalid Choice"
		end

	else
		puts "Invalid Login:-("
	end
end
def uslogin()
	flag = 0
	#csvap = CSV.open("C:\\Ruby24-x64\\Files\\data\\registration.csv","a+")
	csv = CSV.read("registration.csv")
	puts "Enter the username"
	usr = gets.to_i
	puts "Enter your password"
	pass = gets.chomp
    
	for i in 0..csv.length-1
		if (csv[i][3]).to_i==usr and csv[i][4]==pass
			flag = 1
			puts "Login Sucessfull..!!"
			puts ""
			begin
                puts""
                puts""
            puts "which sports do you want to participate"
			puts "1. Soccer"
			puts "2. Basket ball"
			puts "3. Volley ball"
            puts "4. Base ball"
            puts "5. Shuttle"
            puts"6.Back"
			puts ""
			puts "Choose your choice:"
			ch5 = gets.to_i
			case ch5
				when 1
					soccer
				when 2
                    basketball
                when 3
                    volleyball
                when 4
                    baseball
                when 5
                    shhuttle	
				when 6
					break
				else
					puts "Invalid choice"
			end
			end while ch5!=7
		end
	end
	if flag == 0
		puts "Invalid credentials"
	end
end

def registration()
	CSV.open("registration.csv","a+") do |csv|
	#csv<<["Name","Age","Gender","Username","Password"]
	puts "Enter your name"
	uname = gets.chomp
	puts "Enter your Age"
	age = gets.to_i
	puts "Enter your gender"
	gen = gets.chomp
	usr = rand(1000..9999)
	puts "your username is #{usr}"
	puts "Enter your password"
	pass = gets.chomp
	csv<<[uname,age,gen,usr,pass]
        puts""
	puts "Your registration is verified"
        puts""
	puts "Now you are able to register the game"
        puts""
	puts "Please Login to continue :-)"
	
end
end
        puts "************************************--------SPORTS SELECTION------***************************************************"
puts""
begin
puts""
puts "1. For Admin"
puts "2. For User"
puts "3.  Exit"
puts ""
puts "Enter the choice"

ch = gets.to_i
case ch
when 1
	adlogin()
when 2
	begin
	puts ""
	puts "1. User Registration"
	puts "2. Sports login"
	puts "3. Back"
	puts ""
	puts "Enter your choice"
	ch1 = gets.to_i
	puts ""
	case ch1
	when 1
		registration()

	when 2
		uslogin()
	when 3
		break
	else
		puts "Invalid Choice"
	end
	end while ch1!=3
when 3
	break
else
	puts "Invalid choice Entered"
end
end while ch!=3
