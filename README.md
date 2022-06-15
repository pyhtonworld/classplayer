# project4
class Player:
    def __init__(self,firstName,lastName,age,nation):
        self.setFirstName(firstName)
        self.setLastName(lastName)
        self.setNation(nation)
        self.setAge(age)
    
    # Accesors
    def getFirstName(self,):
        return self.__firstName
    def getLastName(self,):
        return self.__lastName
    def getNation(self,):
        return self.__nation
    def getAge(self,):
        return self.__age
    #Mutator
    def setFirstName(self,firstName):
        self.__firstName = firstName
    def setLastName(self,lastName):
        self.__lastName = lastName
    def setNation(self,nation):
        self.__nation = nation
    def setAge(self,age):
        self.__age = age
    #Print Function
    def print_player(self,):
        print("First Name: " + str(self.getFirstName()))
        print("Last Name: " + str(self.getLastName()))
        print("Age: " + str(self.getAge()))
        print("Nation: " + str(self.getNation()))
        
class LeaguePlayer(Player):
    def __init__(self,firstName,lastName,age,nation,branch, game_num, win_num, lost_num , player_score):
        Player.__init__(self,firstName,lastName,age,nation)
        self.setBranch(branch)
        self.setGameNum(game_num)
        self.setWinNum(win_num)
        self.setLostNum(lost_num)
        self.setPlayerScore(player_score)
    # Accesors
    def getBranch(self,):
        return self.__branch
    def getGameNum(self,):
        return self.__game_num
    def getWinNum(self,):
        return self.__win_num
    def getLostNum(self,):
        return self.__lost_num
    def getPlayerScore(self,):
        return self.__player_score
    #Mutator
    def setBranch(self,x):
        self.__branch = x
    def setGameNum(self,x):
        self.__game_num = x
    def setWinNum(self,x):
        self.__win_num = x
    def setLostNum(self,x):
        self.__lost_num = x
    def setPlayerScore(self,x):
        self.__player_score = x
    
    #Statics
    def statistics(self,):
        self.statistics = self.getPlayerScore()/self.getGameNum()
        print("Scores per league game: " + str(self.statistics))
        
    #Print
    def print_player(self,):
        Player.print_player(self,)
        print("Branch: " + str(self.getBranch()))
        print("Number of played league game: " + str(self.getBranch()))
        print("Number of win league game: " + str(self.getWinNum()))
        print("Number of lost league game: " + str(self.getLostNum()))
        print("Number of player score: " + str(self.getPlayerScore()))
    
    #points 
    def points(self,):
        self.points = 10*self.getGameNum() + 3*self.getWinNum() - 2*self.getLostNum()
        return self.points
  
    
    
class NationalPlayer(LeaguePlayer):
    def __init__(self,firstName,lastName,age,nation,branch, game_num, win_num, lost_num , player_score,nationalGame_num ,nationalPlayer_score):
        LeaguePlayer(self,firstName,lastName,age,nation,branch, game_num, win_num, lost_num , player_score)
        self.setNatGameNum(nationalGame_num)
        self.setNatPlayerScore(nationalPlayer_score)
        
    def setNatGameNum(self,nationalGame_num):
        self.__nationalGame_num = nationalGame_num
        
    def setNatPlayerScore(self,nationalPlayer_score):
        self.nationalPlayer_score = nationalPlayer_score
    def print_player(self,):
        LeaguePlayer.print_player(self,)
        print("Number of played Natural Game")

def main():
    my_player = Player("Fabian", "Delph",22, "England")
    my_player.print_player()
    print()
    
    my_league_player = LeaguePlayer("Tony","Parker",28,"France","Basketball",36,17,19,22)
    my_league_player.print_player()
    my_league_player.statistics()
    print("Player Points: ",my_league_player.points())
    
main()    
