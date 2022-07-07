classDiagram
    Duck<|--RedDuck
    Duck<|--BlueDuck
    Duck<|--BlackDuck
    Game <|--GameStatus

    class Duck{
      #Int flyingSpeed
      +Int score
      #Double startXpos
      #Double endXpos
      #Double startYpos
      #Double endYpos
      +quack()
      #updateXendPos()
      #updateYendPos()
      +Boolean isDead()
      +Boolean flewAway()
    }
    class Dog{
        -Int popUpY
        -Int popUpX
        +catchDuck()
        +Sniff()
        +Jump()
        +Giggle()
        +bark()
    }
  class GameStatus{
      -updateScore()
      -updateLevel()
      -updateShot()
      -updateHitCount()
      -updateHitLine()
      +Boolean isGameOver()
      +Boolean isnextLevel()

  }
  class Game{
    +Int level
    +Int Score
    +Int Shot
    -displayScore()
    -displayHitDucks()
    -displayHitLine()
    -displayShot()
    -displayLevel()
    -displayRound()
    -displayDuckScore()
    -gameOver()
    -startGame()
    -nextlevel()

  }
    class Player{
      +Int ShotCount
      +Int hitCount
      +shoot()
      +missShot()
      +successShot()
    }
    
    class RedDuck{
     +redFlying()
     +beingShotRed()
     +redScore()
    }
    class BlueDuck{
     +blueFlying()
     +beingShotBlue()
     +blueScore()
    }
    class BlackDuck{
     +blackFlying()
     +beingShotBlack()
     +blackScore()
    }