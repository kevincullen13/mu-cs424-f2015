Lecture 2: Starting Scheme
==========================
````
Welcome to Racket v6.1.
> 7
7
> sin
#<procedure:sin>
> (sin 1)
0.8414709848078965
> ((sin 1))
application: not a procedure;
 expected a procedure that can be applied to arguments
  given: 0.8414709848078965
  arguments...: [none]
  context...:
   /usr/share/racket/collects/racket/private/misc.rkt:87:7
> (sin (1))
application: not a procedure;
 expected a procedure that can be applied to arguments
  given: 1
  arguments...: [none]
  context...:
   /usr/share/racket/collects/racket/private/misc.rkt:87:7
> sqrt
#<procedure:sqrt>
> *
#<procedure:*>
> +
#<procedure:+>
> (sqrt (+ (* 3 3) (* 4 4)))
5
> (define three (+ 1 2))
> three
3
> (* three three)
9
> (lambda (x) (+ (* x x) 1))
#<procedure>
> (  (lambda (x) (+ (* x x) 1))       three)
10
> (define hypot (lambda (x y) (sqrt (+ (expt x 2) (expt y 2)))))
> (hypot 3 4)
5
> (hypot 6 8)
10
> (hypot 7 8)
10.63014581273465
> (hypot 1 1)
1.4142135623730951
> =
#<procedure:=>
> (= 2 1)
#f
> (= 1 1)
#t
> (zero? 2)
#f
> (zero? 0)
#t
> zero?
#<procedure:zero?>
> one?
one?: undefined;
 cannot reference undefined identifier
  context...:
   /usr/share/racket/collects/racket/private/misc.rkt:87:7
> (define one? (lambda (x) (= x 1)))
> one?
#<procedure:one?>
> (one? 2)
#f
> (if (zero? 3) 7 8)
8
> (if (zero? 0) 7 8)
7
> (/ 1 0)
/: division by zero
  context...:
   /usr/share/racket/collects/racket/private/misc.rkt:87:7
> (if (zero? 1) (/ 1 0) 17)
17
> (if (zero? 0) (/ 1 0) 17)
/: division by zero
  context...:
   /usr/share/racket/collects/racket/private/misc.rkt:87:7
> (define fact (lambda (n) (if (zero? n) 1 (* n (fact (- n 1))))))
> (fact 0)
1
> (fact 1)
1
> (fact 2)
2
> (fact 3)
6
> (fact 30)
265252859812191058636308480000000
> (fact 300)
306057512216440636035370461297268629388588804173576999416776741259476533176716867465515291422477573349939147888701726368864263907759003154226842927906974559841225476930271954604008012215776252176854255965356903506788725264321896264299365204576448830388909753943489625436053225980776521270822437639449120128678675368305712293681943649956460498166450227716500185176546469340112226034729724066333258583506870150169794168850353752137554910289126407157154830282284937952636580145235233156936482233436799254594095276820608062232812387383880817049600000000000000000000000000000000000000000000000000000000000000000000000000
> (fact 3000)
41493596034378540855568670930866121709511191949318099176894676576975585651235319500860007652178003420075184635383617118495750871114045907794553402161068339611621037904199177522062663390179682805164719697495968842457728766097103003726111095340241127118833157738815328438929737613021106312930374401485378725446079610290429491049793888120762511625132917004641668962117590203575175488980653577868915285093782469994674699190832093511068363824287063522268544339213775150488588104036818809099292912497141900508938994404715351473154531587441509960174267875087460367974117072368747277143988920683691618503608198459718093784453523958505377611086511162363145920886108557450874513945305436213711898150847192094426374203275029996333784944014775671414680824207499914714878359669720638954670589960178569480263388767112871068004950827400717124819476386401369193544354120312786601434792549959143530120653103406625503231020738351502195103148673612338739395096551462159349015789949944072311004426924838140141455487872738045856023561583204317945953055830693351246890721246151468485308724031267967089113548982733475375756899365176396424781733462510879015743437398920492267098317033932107176343983352444576040476565400414414699479984354554597799386702839428513413188913165695310848513525094006147774047007331406541794428004436691903685469270857271701648011512057452448607968773784803660653009109815639091294110633715621540903800135058671624262333902434166628716521228590274568833504897926869369792878376894841436573866436955075473964882256222183380014600761196859217603234808467455216330411738004331144225926243690558782914907973885758784585739828695390302383837265882427654306437517757897215045071361801730051628424476294227485755627828763498767195281368913583918824499284741591683130334032199946752082914885764345863832313545205075955912062067273296951386122994658607527317884452449865348164169238844889061495850934373442889814884427321817131272533891534506581143823381205875379808605080889761753882896252933633750454549168600267229591225528854584482686655324313011353754812409561237686078007700707939541848907149467377854407528307872988103912945121929864793703451257436445581459757140822705986325165352906584571123585270211933452981105568398809884094980346185078025273038736784042169427237980464304250045030806637032760016341921442805708802430850567892108646977455139539119838636167190300278146380136932482332771595180596193069504237836082620570887209297929797429404576877338319877444685544294800321741056689423710545028870419611915072739000031642014474213323293871618029555614004602867400422885389854650328028428515122296028795741801621823236098320971441047012533067314896153236788734984553949604397050352347766211395914519270422122231426998692087463520980686224354813376194395131942868113486531562228173214976481705381846155326596187530296478601160872263640443922257601926494610916885151013143945574398303192557154162151442469122370519149097861849436150963109933639594561796593396851958605338631176324147066842257192394742531726479559749993283247279807896470753054014194090200609712674753186365525403212757757853930697530056595208207457499471898144453772248207888443335118545601568853708182892895218300139654376947286418776665762815389737340159410543681435437346134244692067070082782423645557450882556670157242752810317141640631410681384330924027281318960884813040665226169552825637183862464944295688859393846726723694199475571320546018263425731029115353532728808182773021596787088437293412117084511580629967697266601663635276959969021502122104954259567278593185516268447100374434620422003535391203738393095420695021486207390653190910821344334251497896284236198571674773848126097443055036250866354720730971298084697196537722779893160200560725058007512407494448163392214398118492748281978655178478547749198714138485042290383954090570842038137277135667703565041081780520695032136233521692740531015340921761834078817735674646749071616600653230438902639786065509005309872435445689315601329942407112295015453771521051942445512795364971214872222193729289159833001742397977592530501318837883494884232222507318816399438935627817102875432588794558857742780390717166381257903798149148445526885871629931014510733215554773264576035916184298708323237568837917135073006026738292294687081030751946020376438138677107333779312582257356435534577162804030480925785909747233413932904072239860005448269296110393640127539539899397420021925268928622564959279136369546983247314494094297494213208716963662812963846191378114609210701033012119934264941666449130310898493535366401831282683112506578386425906537197010907276429330534751297336716929415047870949241778121534979499449732358445130210029720359993576507730563696950539990891252004810120090569633144368179194247963563389102486250773367249399801723451627048850149438343735826440053481474957421328873648479589553843836378275601433377798816126854462406494134416119108952653326761627660221130879211665924379496534838030236064294981985541014311566601739518539426008673198564586684635442730180022292607589767192198367529528365158715521887698317999005853121518691037776676883654291247419826099434535671529412823837612115555686210454583810355154404953718470726363218532775486501811002621331228429860926112159573066023932077476742800909462674322138805290643067711276964013735906251051050623568241317651533030775358975134565147424167401517470720839101869989993279364910892687924739705814152855543965954222603919059265825637344676406359525838966981511983959886603683753042017990328185945569412550519066302854869533377682984600031808093822130038102214387057461181304251961916405970456035183121708151658647356556540532928411748628957082856792300053525846377061280591452035546389932127875906349627837975871352588618213252263577038396202737385324908353680497990085701522483303439525197344653342994652565236096742834550523739733902374261808871799283722285366293439240895762913154442106573609205481842139365893867715542842477275100166734357743093638948444564764377184073874379471007867151070449554657626281566137550730763768080600031844296233977808233311359787577136983012817571625671683287281511937336685789437109097748581222868126824122317272681184975207863453107495331708260153159440253645365524453587952034745213429248916644504804355352281977721981971869054884176896398782704782066126921472548618247859626434279190274503452994769367997217285165465591799471789067885687278574470084289723778234763080740919512966238346427839653865017324665850192144091694630371265581197700774682562035198318782913591013997817303635173764706714383992810291224460848320518983248348855131025539721583184931653670732273172995431750775475634748127320956655431851879586978172491721700865768098908327830838240437737974455342525688712898855513180967012497859454290609627370590659970784172738420721605576789060565167694565490120388165775861939230924362983389549857279874523398090499858467484850399509109398834210424693113617875978611803096108774362764990414655167545507613665725914993376114340243762910290384135888531312591132544849225896007184851169390193985434649415483782338302531368775990005443722332901462568184095998830522521585328599833990336595418932696680163265899358234663247080324020429791357425755498549372896192091650794671997121439832581553945835125648010889886887056882711222628734035772418424803231173027338442220604015609242079569493204943809402465562530303328824165302038006041288444384884189129393985971765670211501611340121169355535864984802941563238279447576315042685734269863116562800932164578165410411899078396210758605145091526528422433647230880469088426412525126584729134059195171754291152622002229756986927959124620964363057052133099216422258437651889193630329851223282950806126200573565554213183555838289318138795940962303792777230344423432341561603558590502324475274502630869831414125396371754413611897269158650716722308083435295578401087236027347001118786146233185439431057058483770474806035004556885020602730222256397630738939985024978155182679916994164145540329909813190506654358156657691529068908186204138444091456355291242064901717436430473455191375922914953282988151808740076733486997695322871450791584448703980405737673555777873593937891577147956023340708456392314170118392555234618119775915673385955919265270624063734277760215846511035368057963320714896942663358570375305829676608224208465464558556667889222627619990263961792637457851652540918756608543859661221944248720424960000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
> (/ (fact 3000) (fact 2999))
3000
> (fact 0.5)
  C-c C-cuser break
> (define fact (lambda (n) (if (<= n 0) 1 (* n (fact (- n 1))))))
> (/ (fact 3000) (fact 2999))
3000
> (fact 0.5)
0.5
> (define fact (lambda (n) (if (zero? n) 1 (* n (fact (- n 1))))))
> (load "lecture-02.scm")
> (load "lecture-02.scm")
> (load "lecture-02.scm")
> (make-pair 8 9)
#<procedure:...4/lecture-02.scm:10:4>
> (define fred (make-pair 8 9))
> (get-fst fred)
8
> (get-snd fred)
9
> (load "lecture-02.scm")
> (define george (make-pair2 3 4))
> (get-fst2 george)
3
> (get-snd2 george)
4
> (define sam (make-pair2 (make-pair2 3 4) (make-pair2 5 (make-pair2 6 7))))
> (get-fst2 (get-fst2 sam))
3
> (get-snd2 (get-fst2 sam))
4
> (get-snd2 (get-snd2 (get-snd2 sam)))
7
> (get-fst2 sam)
#<procedure:...4/lecture-02.scm:20:4>
> list
#<procedure:list>
> (list 2 3 4 5)
(2 3 4 5)
> (list 2 (list 3 4) 5)
(2 (3 4) 5)
> (list)
()
> (list 3)
(3)
> (list (list 3))
((3))
> (define bob (list 1 (list 2 3 4) (list) 5))
> bob
(1 (2 3 4) () 5)
> (car bob)
1
> (cdr bob)
((2 3 4) () 5)
> (cdr (cdr bob))
(() 5)
> (cdr (cdr (cdr bob)))
(5)
> (cdr (cdr (cdr (cdr bob))))
()
> (car (cdr (cdr (cdr bob))))
5
> (cadddr bob)
5
> (caddr bob)
()
> (cadr bob)
(2 3 4)
> (null? bob)
#f
> (null? (cddddr bob))
#t
> (cons 5 (list))
(5)
> bob
(1 (2 3 4) () 5)
> (cons 7 bob)
(7 1 (2 3 4) () 5)
> bob
(1 (2 3 4) () 5)
> (list 1 2 3 4)
(1 2 3 4)
> (cons 1 (cons 2 (cons 3 (cons 4 (list)))))
(1 2 3 4)
> null
()
> null?
#<procedure:null?>
> (cons 1 (cons 2 (cons 3 (cons 4 null))))
(1 2 3 4)
> (length (cons 1 (cons 2 (cons 3 (cons 4 null)))))
4
> (length bob)
4
> (length (cdr bob))
3
> (load "lecture-02.scm")
> (my-length (cdr bob))
3
> "foo"
"foo"
> car
#<procedure:car>
> (quote car)
car
> (cons (quote car) (cons 3 null))
(car 3)
> (eq? (quote car) (quote cdr))
#f
> (eq? (quote car) (quote car))
#t
> (number? 3)
#t
> (symbol? 3)
#f
> (symbol? (quote foo))
#t
> (symbol? "foo")
#f
> (symbol->string (quote foo))
"foo"
> (string->symbol "bazonk")
bazonk
````
* File: lecture-02.scm
````scheme
(define fact
  (λ (n)
    (if (zero? n)
	1
	(* n
	   (fact (- n 1))))))

(define make-pair
  (λ (x y)
    (λ (z) (if z x y))))

(define get-fst
  (λ (p) (p #t)))

(define get-snd
  (λ (p) (p #f)))

(define make-pair2
  (λ (x y)
    (λ (z) (z x y))))

(define get-fst2
  (λ (p) (p (λ (x y) x))))

(define get-snd2
  (λ (p) (p (λ (x y) y))))

(define my-length
  (λ (xs)
    (if (null? xs)
	0
	(+ 1 (my-length (cdr xs))))))
````