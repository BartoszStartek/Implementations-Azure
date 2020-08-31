Na tapetę wziąłem zwykły Storage Account sądząc, że tam gdzie dane będzie najwięcej opcji ich zabezpieczeń.<br/>
To co możemy zaliczyć do security:<br/>
-Access control (IAM) - przypisywanie ról użytkownikom, decydowanie kto co może, w jakim zakresie itp.,<br/>
-Access Keys - klucze dostępowe służące do np. uwierzytelniania połączenia do naszych zasobów przez CLI czy SDK. Klucze można w każdym momencie wygenerować na nowo,<br/>
-Encryption - dane standardowo przy tworzeniu konta magazynu są szyfrowane kluczami Microsoftu i deszyfrowane gdy pobieramy je z powrotem.<br/> Oprócz tego można wybrać szyfrowanie np. przy użyciu kluczy z Key Vault,
-Shared access signature (SAS) - generowanie identyfikatorów dostępu np. dla mniej zaufanych osób, klientów.<br/> Można dokładnie określić zakres dostępu (read/write/delete/create itp.), ale co ważne można wskazać datę i godzinę startu i zakończenia działania identyfikatora,<br/>
-Firewall and virtual networks - konfigurowanie ustawień zapory,<br/>
-Private endpoint connections - jak nazwa wskazuje, tworzenie prywatnych punktów końcowych służących do łączenia się z usługą,<br/>
-Advanced Security (Security Center) - zaawansowane narzędzie do zarządzania bezpieczeństwem. Fajną możliwością jest monitorowanie naszych zasobów i sprawdzanie,<br/> które mają luki w zabezpieczeniach lub zostały źle zabezpieczone.<br/> 
-Locks - służy do blokowania operacji na zasobach(read-only,delete), <br/>
-Activity log - możliwość śledzenia wszystkich wykonanych operacji. Można logi wyeksportować do innego formatu. 
