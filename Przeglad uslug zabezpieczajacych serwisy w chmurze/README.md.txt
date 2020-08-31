Na tapetê wzi¹³em zwyk³y Storage Account s¹dz¹c, ¿e tam gdzie dane bêdzie najwiêcej opcji ich zabezpieczeñ. Chyba siê nie myli³em.
To co mo¿emy zaliczyæ do security:
-Access control (IAM) - przypisywanie ról u¿ytkownikom, decydowanie kto co mo¿e, w jakim zakresie itp.,
-Access Keys - klucze dostêpowe s³u¿¹ce do np. uwierzytelniania po³¹czenia do naszych zasobów przez CLI czy SDK. Klucze mo¿na w ka¿dym momencie wygenerowaæ na nowo,
-Encryption - dane standardowo przy tworzeniu konta magazynu s¹ szyfrowane kluczami Microsoftu i deszyfrowane gdy pobieramy je z powrotem. Oprócz tego mo¿na wybraæ szyfrowanie np. przy u¿yciu kluczy z Key Vault,
-Shared access signature (SAS) - generowanie identyfikatorów dostêpu np. dla mniej zaufanych osób, klientów. Mo¿na dok³adnie okreœliæ zakres dostêpu (read/write/delete/create itp.), ale co wa¿ne mo¿na wskazaæ datê i godzinê startu i zakoñczenia dzia³ania identyfikatora,
-Firewall and virtual networks - konfigurowanie ustawieñ zapory,
-Private endpoint connections - jak nazwa wskazuje, tworzenie prywatnych punktów koñcowych s³u¿¹cych do ³¹czenia siê z us³ug¹,
-Advanced Security (Security Center) - zaawansowane narzêdzie do zarz¹dzania bezpieczeñstwem. Fajn¹ mo¿liwoœci¹ jest monitorowanie naszych zasobów i sprawdzanie, które maj¹ luki w zabezpieczeniach lub zosta³y Ÿle zabezpieczone. 
-Locks - s³u¿y do blokowania operacji na zasobach(read-only, delete),
-Activity log - mo¿liwoœæ œledzenia wszystkich wykonanych operacji. Mo¿na logi wyeksportowaæ do innego formatu. 
