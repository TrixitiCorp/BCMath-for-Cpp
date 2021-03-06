BC-Math for Qt and C++ (Equivalent BigDecimal in Java)
===========

BC-Math PHP (https://php.net/manual/en/intro.bc.php) Adapted to Qt and STL C++. Tested only in Qt5.


BC Math Functions for Qt
===========

- QBCMath::bcadd: Add two arbitrary precision numbers (https://php.net/manual/en/function.bcadd.php)
    
- QBCMath::bccomp: Compare two arbitrary precision numbers (https://php.net/manual/en/function.bccomp.php)
    
- QBCMath::bcdiv: Divide two arbitrary precision numbers (https://php.net/manual/en/function.bcdiv.php)
    
- QBCMath::bcmod: Get modulus of an arbitrary precision number (https://php.net/manual/en/function.bcmod.php)
    
- QBCMath::bcmul: Multiply two arbitrary precision numbers (https://php.net/manual/en/function.bcmul.php)
    
- QBCMath::bcpow: Raise an arbitrary precision number to another (https://php.net/manual/en/function.bcpow.php)
    
- QBCMath::bcscale: Set default scale parameter for all bc math functions (https://php.net/manual/en/function.bcscale.php)
    
- QBCMath::bcsub: Subtract one arbitrary precision number from another (https://php.net/manual/en/function.bcsub.php)

- QBCMath::bcround: Round decimals, receives a single parameter to determine how many decimal places should be.
    
    
BC Math Functions for STL C++
===========

- BCMath::bcadd: Add two arbitrary precision numbers (https://php.net/manual/en/function.bcadd.php)
    
- BCMath::bccomp: Compare two arbitrary precision numbers (https://php.net/manual/en/function.bccomp.php)
    
- BCMath::bcdiv: Divide two arbitrary precision numbers (https://php.net/manual/en/function.bcdiv.php)
    
- BCMath::bcmod: Get modulus of an arbitrary precision number (https://php.net/manual/en/function.bcmod.php)
    
- BCMath::bcmul: Multiply two arbitrary precision numbers (https://php.net/manual/en/function.bcmul.php)
    
- BCMath::bcpow: Raise an arbitrary precision number to another (https://php.net/manual/en/function.bcpow.php)
    
- BCMath::bcscale: Set default scale parameter for all bc math functions (https://php.net/manual/en/function.bcscale.php)
    
- BCMath::bcsub: Subtract one arbitrary precision number from another (https://php.net/manual/en/function.bcsub.php)

- BCMath::bcround: Round decimals, receives a single parameter to determine how many decimal places should be.
        
    
USAGE (Qt)
===========

Copy in your project only bcmath.h and bcmath.cpp and add next line in your header:

    #include "bcmath.h"
    

Code Test (Qt)
===========
    
    QBCMath::bcscale(4); //Num Decimals
    QBCMath test("-5978");
    
    test^=30; //Pow, only integers. Not work decimals.
    qDebug()<<"Result BigDecimal 1: "<<test.toString().toStdString().c_str();
    
    test-=1.23; //sub
    qDebug()<<"Result BigDecimal 2: "<<test.toString().toStdString().c_str();
    
    test*=1.23; //mul
    qDebug()<<"Result BigDecimal 3: "<<test.toString().toStdString().c_str();
    
    test*=-1.23; //mul
    qDebug()<<"Result BigDecimal 4: "<<test.toString().toStdString().c_str();

    QBCMath::bcscale(70); //Num Decimals
    
    QBCMath randNum("-5943534512345234545.8998928392839247844353457");
    QBCMath pi("3.1415926535897932384626433832795028841971693993751058209749445923078164062862");

    QBCMath result1 = randNum + pi;
    QBCMath result2 = randNum - pi;
    QBCMath result3 = randNum * pi;
    QBCMath result4 = randNum / pi;

    qDebug()<<"Result Super Precision 1: "<<result1.toString().toStdString().c_str();
    qDebug()<<"Result Super Precision 2: "<<result2.toString().toStdString().c_str();
    qDebug()<<"Result Super Precision 3: "<<result3.toString().toStdString().c_str();
    qDebug()<<"Result Super Precision 4: "<<result4.toString().toStdString().c_str();
    
    //Other example
    QBCMath::bcscale(4); //Num Decimals
    qDebug()<<"Other 1: "<<QBCMath::bcmul("1000000.0134", "8.0234").toStdString().c_str();
    qDebug()<<"Other 2: "<<QBCMath::bcadd("1000000.0134", "8.0234").toStdString().c_str();
     
    qDebug()<<"Compare 1:  "<<QBCMath::bccomp("1", "2");
    qDebug()<<"Compare 2:  "<<QBCMath::bccomp("1.00001", "1", 3); 
    qDebug()<<"Compare 3:  "<<QBCMath::bccomp("1.00001", "1", 5);
    qDebug()<<"Compare 4:  "<<(QBCMath("1")< QBCMath("2"));
    qDebug()<<"Compare 5:  "<<(QBCMath("1")<=QBCMath("2"));
    qDebug()<<"Compare 6:  "<<(QBCMath("1")> QBCMath("2"));
    qDebug()<<"Compare 7:  "<<(QBCMath("1")>=QBCMath("2"));
    qDebug()<<"Compare 8:  "<<(QBCMath("2")< QBCMath("2"));
    qDebug()<<"Compare 9:  "<<(QBCMath("2")<=QBCMath("2"));
    qDebug()<<"Compare 10: "<<(QBCMath("2")> QBCMath("2"));
    qDebug()<<"Compare 11: "<<(QBCMath("2")>=QBCMath("2"));
    
    qDebug()<<"Round 1: "<<QBCMath::bcround("123.01254").toStdString().c_str();
    qDebug()<<"Round 2: "<<QBCMath::bcround("-123.01254", 3).toStdString().c_str();
    qDebug()<<"Round 3: "<<QBCMath::bcround("123.01254", 2).toStdString().c_str();
    pi.round(3);
    qDebug()<<"Round 4: "<<pi.toString().toStdString().c_str();

    QBCMath part1("-.123");
    QBCMath part2(".123");
    QBCMath part3("123");
    qDebug()<<"Int part 1: "<<part1.getIntPart().toStdString().c_str();
    qDebug()<<"Dec part 1: "<<part1.getDecPart().toStdString().c_str();
    qDebug()<<"Int part 2: "<<part2.getIntPart().toStdString().c_str();
    qDebug()<<"Dec part 2: "<<part2.getDecPart().toStdString().c_str();
    qDebug()<<"Int part 3: "<<part3.getIntPart().toStdString().c_str();
    qDebug()<<"Dec part 3: "<<part3.getDecPart().toStdString().c_str();

USAGE (STL C++)
===========

Copy in your project only bcmath_stl.h and bcmath_stl.cpp and add next line in your header:

    #include "bcmath_stl.h"

Code Test (STL C++)
===========

    BCMath::bcscale(4); //Num Decimals
    BCMath test("-5978");

    test^=30; //Pow, only integers. Not work decimals.
    std::cout<<"Result BigDecimal 1: "<<test.toString().c_str()<<std::endl;

    test-=1.23; //sub
    std::cout<<"Result BigDecimal 2: "<<test.toString().c_str()<<std::endl;

    test*=1.23; //mul
    std::cout<<"Result BigDecimal 3: "<<test.toString().c_str()<<std::endl;

    test*=-1.23; //mul
    std::cout<<"Result BigDecimal 4: "<<test.toString().c_str()<<std::endl;

    BCMath::bcscale(70); //Num Decimals

    BCMath randNum("-5943534512345234545.8998928392839247844353457");
    BCMath pi("3.1415926535897932384626433832795028841971693993751058209749445923078164062862");

    BCMath result1 = randNum + pi;
    BCMath result2 = randNum - pi;
    BCMath result3 = randNum * pi;
    BCMath result4 = randNum / pi;

    std::cout<<"Result Super Precision 1: "<<result1.toString().c_str()<<std::endl;
    std::cout<<"Result Super Precision 2: "<<result2.toString().c_str()<<std::endl;
    std::cout<<"Result Super Precision 3: "<<result3.toString().c_str()<<std::endl;
    std::cout<<"Result Super Precision 4: "<<result4.toString().c_str()<<std::endl;

    //Other example
    BCMath::bcscale(4); //Num Decimals
    std::cout<<"Other 1: "<<BCMath::bcmul("1000000.0134", "8.0234").c_str()<<std::endl;
    std::cout<<"Other 2: "<<BCMath::bcadd("1000000.0134", "8.0234").c_str()<<std::endl;

    std::cout<<"Compare 1:  "<<BCMath::bccomp("1", "2")<<std::endl;
    std::cout<<"Compare 2:  "<<BCMath::bccomp("1.00001", "1", 3)<<std::endl;
    std::cout<<"Compare 3:  "<<BCMath::bccomp("1.00001", "1", 5)<<std::endl;
    std::cout<<"Compare 4:  "<<(BCMath("1")< BCMath("2"))<<std::endl;
    std::cout<<"Compare 5:  "<<(BCMath("1")<=BCMath("2"))<<std::endl;
    std::cout<<"Compare 6:  "<<(BCMath("1")> BCMath("2"))<<std::endl;
    std::cout<<"Compare 7:  "<<(BCMath("1")>=BCMath("2"))<<std::endl;
    std::cout<<"Compare 8:  "<<(BCMath("2")< BCMath("2"))<<std::endl;
    std::cout<<"Compare 9:  "<<(BCMath("2")<=BCMath("2"))<<std::endl;
    std::cout<<"Compare 10: "<<(BCMath("2")> BCMath("2"))<<std::endl;
    std::cout<<"Compare 11: "<<(BCMath("2")>=BCMath("2"))<<std::endl;

    std::cout<<"Round 1: "<<BCMath::bcround("123.01254").c_str()<<std::endl;
    std::cout<<"Round 2: "<<BCMath::bcround("-123.01254", 3).c_str()<<std::endl;
    std::cout<<"Round 3: "<<BCMath::bcround("123.01254", 2).c_str()<<std::endl;
    pi.round(3);
    std::cout<<"Round 4: "<<pi.toString().c_str()<<std::endl;

    BCMath part1("-.123");
    BCMath part2(".123");
    BCMath part3("123");
    std::cout<<"Int part 1: "<<part1.getIntPart().c_str()<<std::endl;
    std::cout<<"Dec part 1: "<<part1.getDecPart().c_str()<<std::endl;
    std::cout<<"Int part 2: "<<part2.getIntPart().c_str()<<std::endl;
    std::cout<<"Dec part 2: "<<part2.getDecPart().c_str()<<std::endl;
    std::cout<<"Int part 3: "<<part3.getIntPart().c_str()<<std::endl;
    std::cout<<"Dec part 3: "<<part3.getDecPart().c_str()<<std::endl;


Result
===========

    Result BigDecimal 1:  198005530669253749533290222782634796336450786581284861381777714804795900171726938603997395193921984842256586113024
    Result BigDecimal 2:  198005530669253749533290222782634796336450786581284861381777714804795900171726938603997395193921984842256586113022.7700
    Result BigDecimal 3:  243546802723182111925946974022640799493834467494980379499586589209898957211224134482916796088524041355975600919018.0071
    Result BigDecimal 4:  -299562567349513997668914778047848183377416395018825866784491504728175717369805685413987659188884570867849989130392.1487

    Result Super Precision 1:  -5943534512345234542.7583001856941315459727023167204971158028306006248941790250554076921835
    Result Super Precision 2:  -5943534512345234549.0414854928737180228979890832795028841971693993751058209749445923078164
    Result Super Precision 3:  -18672164360341183116.9114783895073349180904753962992796943871920962352436079118338887287186
    Result Super Precision 4:  -1891885794154043400.2804849527556211973567525043250278948318788149660700494315139982452600
    
    Other 1:  8023400.1075
    Other 2:  1000008.0368
    
    Compare 1:   -1
    Compare 2:   0
    Compare 3:   1
    Compare 4:   true
    Compare 5:   true
    Compare 6:   false
    Compare 7:   false
    Compare 8:   false
    Compare 9:   true
    Compare 10:  false
    Compare 11:  true
    
    Round 1:  123.0125
    Round 2:  -123.013
    Round 3:  123.01
    Round 4:  3.142
    
    Int part 1:  -0
    Dec part 1:  123
    Int part 2:  0
    Dec part 2:  123
    Int part 3:  123
    Dec part 3:  0