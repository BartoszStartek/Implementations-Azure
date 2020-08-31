Na tapet� wzi��em zwyk�y Storage Account s�dz�c, �e tam gdzie dane b�dzie najwi�cej opcji ich zabezpiecze�. Chyba si� nie myli�em.
To co mo�emy zaliczy� do security:
-Access control (IAM) - przypisywanie r�l u�ytkownikom, decydowanie kto co mo�e, w jakim zakresie itp.,
-Access Keys - klucze dost�powe s�u��ce do np. uwierzytelniania po��czenia do naszych zasob�w przez CLI czy SDK. Klucze mo�na w ka�dym momencie wygenerowa� na nowo,
-Encryption - dane standardowo przy tworzeniu konta magazynu s� szyfrowane kluczami Microsoftu i deszyfrowane gdy pobieramy je z powrotem. Opr�cz tego mo�na wybra� szyfrowanie np. przy u�yciu kluczy z Key Vault,
-Shared access signature (SAS) - generowanie identyfikator�w dost�pu np. dla mniej zaufanych os�b, klient�w. Mo�na dok�adnie okre�li� zakres dost�pu (read/write/delete/create itp.), ale co wa�ne mo�na wskaza� dat� i godzin� startu i zako�czenia dzia�ania identyfikatora,
-Firewall and virtual networks - konfigurowanie ustawie� zapory,
-Private endpoint connections - jak nazwa wskazuje, tworzenie prywatnych punkt�w ko�cowych s�u��cych do ��czenia si� z us�ug�,
-Advanced Security (Security Center) - zaawansowane narz�dzie do zarz�dzania bezpiecze�stwem. Fajn� mo�liwo�ci� jest monitorowanie naszych zasob�w i sprawdzanie, kt�re maj� luki w zabezpieczeniach lub zosta�y �le zabezpieczone. 
-Locks - s�u�y do blokowania operacji na zasobach(read-only, delete),
-Activity log - mo�liwo�� �ledzenia wszystkich wykonanych operacji. Mo�na logi wyeksportowa� do innego formatu. 
