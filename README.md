# LV2_ralasic

Poštovani, ispirčavam se, znam da ste me uspozorili ali još ovaj puta cu predati zadatke samo ovako zalijpljene tu.. 
Obječajem da cu idući puta pogledati one video zapise koje ste mi poslali i napraviti po njima git.
Predajem samo prva tri zadatka..


namespace IvanRalasic
{

    class Program // prvi, drugi i treci zadatak program jednak
    
    {
        static void Main(string[] args)
        
        {
        
            Die die1 = new Die(6);//znam da ovo nije dobar nacin dodavanja i da ste savili 200 komada
            Die die2 = new Die(6);//ne bi funkcioniralo ali nadam se da ce zadovoljiti formu
            Die die3 = new Die(6);
            Die die4 = new Die(6);
            Die die5 = new Die(6);
            Die die6 = new Die(6);
            Die die7 = new Die(6);
            Die die8 = new Die(6);
            Die die9 = new Die(6);
            Die die10 = new Die(6);
            Die die11 = new Die(6);
            Die die12 = new Die(6);
            Die die13 = new Die(6);
            Die die14 = new Die(6);
            Die die15 = new Die(6);
            Die die16 = new Die(6);
            Die die18 = new Die(6);
            Die die19 = new Die(6);
            Die die20 = new Die(6);
            

            DiceRoller diceRoller = new DiceRoller();

            diceRoller.InsertDie(die1);
            diceRoller.InsertDie(die2);
            diceRoller.InsertDie(die3);
            diceRoller.InsertDie(die4);
            diceRoller.InsertDie(die5);
            diceRoller.InsertDie(die6);
            diceRoller.InsertDie(die7);
            diceRoller.InsertDie(die8);
            diceRoller.InsertDie(die9);
            diceRoller.InsertDie(die10);
            diceRoller.InsertDie(die11);
            diceRoller.InsertDie(die12);
            diceRoller.InsertDie(die13);
            diceRoller.InsertDie(die14);
            diceRoller.InsertDie(die15);
            diceRoller.InsertDie(die16);
            diceRoller.InsertDie(die17);
            diceRoller.InsertDie(die18);
            diceRoller.InsertDie(die19);
            diceRoller.InsertDie(die20);

            diceRoller.RollAllDice();

            IList<int> list = new List<int>();
            list = diceRoller.GetRollingResults();

            foreach(int i in list)
            {
                Console.Write(i + " ");
            }
            Console.WriteLine("");
        }
    }
}


namespace IvanRalasic

{
    class Die//prvi zadatak
    
    {
        private int numberOfSides;
        private Random randomGenerator;
        public Die(int numberOfSides)
        {
            this.numberOfSides = numberOfSides;
            this.randomGenerator = new Random();
        }
        public int Roll()
        {
            int rolledNumber = randomGenerator.Next(1, numberOfSides + 1);
            return rolledNumber;
        }
    }
}
namespace IvanRalasic

{
    class Die//drugi zadatak
    
    {
        private int numberOfSides;
        private Random randomGenerator;
        public Die(int numberOfSides, Random random)
        {
            this.numberOfSides = numberOfSides;
            this.randomGenerator = random;
        }
        public int Roll()
        {
            int rolledNumber = randomGenerator.Next(1, numberOfSides + 1);
            return rolledNumber;
        }
    }
}

namespace IvanRalasic
{

    class Die//treci zadatak
    
    {
    
        private int numberOfSides;
        public Die(int numberOfSides)
        {
            this.numberOfSides = numberOfSides;
        }
        public int Roll()
        {
            int rolledNumber = RandomGenerator.GetInstance().NextInt(1, numberOfSides + 1);
            return rolledNumber;
        }
    }
}


namespace IvanRalasic

{
    class DiceRoller//isto za treci
    
    {
    
        private List<Die> dice;
        private List<int> resultForEachRoll;
        public DiceRoller()
        {
            this.dice = new List<Die>();
            this.resultForEachRoll = new List<int>();
        }
        public void InsertDie(Die die)
        {
            dice.Add(die);
        }
        public void RollAllDice()
        {
            
            this.resultForEachRoll.Clear();
            foreach (Die die in dice)
            {
                this.resultForEachRoll.Add(die.Roll());
            }
        }
        
        public IList<int> GetRollingResults()
        {
            return new System.Collections.ObjectModel.ReadOnlyCollection<int>(
           this.resultForEachRoll
           );
        }
        public int DiceCount
        {
            get { return dice.Count; }
        }
    }
}



namespace IvanRalasic
{
    class RandomGenerator//treci zadatak
    
    {
    
        private static RandomGenerator instance; 
        private Random random;
        private RandomGenerator()
        {
            this.random = new Random();
        }
        
        public static RandomGenerator GetInstance()
        {
            if (instance == null)
                instance = new RandomGenerator();
            return instance;
        }
        public int NextInt(int lowerBound, int upperBound)
        {
            return random.Next(lowerBound, upperBound);
        }
    }
}
