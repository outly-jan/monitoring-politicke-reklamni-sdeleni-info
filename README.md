# Monitoring politické reklamy – OOH

Webová aplikace pro podporu terénního monitoringu politické reklamy v souladu s **Nařízením Evropského parlamentu a Rady (EU) 2024/900** o transparentnosti a cílení politické reklamy.

## O projektu

Jde o **osobní projekt**, který jsem vytvořil jako vlastní iniciativu – ruční vyplňování záznamů z terénního monitoringu mi přišlo zdlouhavé, takže jsem s pomocí [Claude Code](https://claude.ai/code) napsal tuto aplikaci. Aplikaci jsem následně poskytl k použití **Úřadu pro dohled nad hospodařením politických stran a politických hnutí (ÚDHPSH)**, jehož kontroloři ji využívají při terénním monitoringu outdoorové politické reklamy (billboardy, bigboardy, citylighty, plakáty apod.).

Nejde o oficiální nástroj ani produkt úřadu.

Aplikace je nasazena jako privátní webová služba přístupná oprávněným zaměstnancům úřadu.

## Co aplikace dělá

Kontrolor v terénu:

1. **Pořídí fotodokumentaci** reklamního nosiče (celkový pohled, detail vizuálu, označení plochy, QR kód).
2. **Nahraje fotografie** do aplikace – ta automaticky vyčte z EXIF metadat datum, čas a GPS polohu, doplní adresu umístění a zobrazí mapu.
3. **QR kód** na reklamě je automaticky přečten; aplikace stáhne odkazovanou stránku s oznámením o transparentnosti a pomocí AI ověří přítomnost povinných náležitostí podle nařízení EU 2024/900.
4. Kontrolor **doplní nebo upraví** zjištěné údaje a výsledek kontrolního checklist.
5. Aplikace **vygeneruje podklady pro úřední záznam** ve formátu `.docx`, které kontrolor vloží do úředního záznamu v systému spisové služby.

## Právní základ

Nařízení Evropského parlamentu a Rady **(EU) 2024/900** ze dne 13. března 2024 o transparentnosti a cílení politické reklamy ukládá zadavatelům politické reklamy povinnost připojovat k reklamním sdělením oznámení o transparentnosti s povinnými náležitostmi. ÚDHPSH je příslušným orgánem pro výkon dozoru v České republice.

## Technologie

- **Frontend / backend:** [Streamlit](https://streamlit.io) (Python)
- **Generování dokumentů:** python-docx
- **Zpracování fotografií:** Pillow, piexif
- **Čtení QR kódů:** pyzbar
- **Mapové podklady a geokódování:** [Mapy.cz API](https://api.mapy.cz) (Seznam a.s.)
- **Analýza transparentnosti:** Claude API (Anthropic)
- **Nasazení:** Streamlit Community Cloud

## Kontakt

Jan Outlý  
[jan@outly.cz](mailto:jan@outly.cz)
