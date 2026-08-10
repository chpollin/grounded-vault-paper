---
type: chapter
status: grounded
checked: {}
assertions:
  - "[[30_assertions/generated-citations-often-fail-to-support-their-sentences]]"
  - "[[30_assertions/source-binding-lowers-unsupported-citation-without-eliminating-it]]"
  - "[[30_assertions/resolvable-citation-without-support-is-a-distinct-error-class]]"
  - "[[30_assertions/attribution-is-separate-from-correctness]]"
  - "[[30_assertions/historical-method-separates-origin-check-from-credibility]]"
  - "[[30_assertions/card-index-organizes-knowledge-as-addressable-linked-notes]]"
  - "[[30_assertions/critical-apparatus-binds-reading-to-witnesses]]"
  - "[[30_assertions/prov-validity-is-internal-consistency]]"
  - "[[30_assertions/llm-summaries-broaden-the-scope-of-findings]]"
posits: 4
created: 2026-08-10
updated: 2026-08-10
---

# Die Stützungslücke

Eine Quellenangabe, die auflöst, ist noch kein Beleg. In einem Audit generativer Suchmaschinen stützten nur 74,5 Prozent der Zitate den Satz, an dem sie hängen, und nur 51,5 Prozent der Sätze waren vollständig durch ihre Zitate gedeckt.[^1] Erfundene Referenzen sind messbar verbreitet, 55 Prozent der Werke, die GPT-3.5 in generierten Papers zitierte, existierten nicht, bei GPT-4 waren es 18 Prozent, und drei kommerzielle juristische Recherchewerkzeuge halluzinieren in 17 bis 33 Prozent der Fälle, eine Rate, die ihre Studie als gegenüber GPT-4 reduziert berichtet.[^2] Der schwerer zu entdeckende Fall ist der andere. Eine Antwort zitiert reale Dokumente und belegt trotzdem falsch, weil das Zitat seine Quelle fehlinterpretiert oder eine unpassende nennt. Wer das finden will, muss die zitierten Texte öffnen, lesen, ihre Autorität einschätzen und sie mit der Behauptung vergleichen.[^3]

Die NLP-Forschung behandelt die Zuordnungsfrage als eigene Größe. Attribution meint den akkuraten Gebrauch von Quelldokumenten zur Stützung generierten Texts, geprüft gegen die mitgelieferte Quelle und ausdrücklich ohne absolutes Urteil über die Faktizität der Aussage.[^4] Eine Trennung ähnlicher Bauart kennt die historische Methodenlehre aus ihren klassischen Handbüchern, die Prüfung der Überlieferung und der Herkunft einer Quelle geht der Prüfung ihrer Glaubwürdigkeit voraus, und beide sind eigene Arbeitsschritte.[^5] Beide Trennungen halten die Zuordnung einer Aussage zu ihrer Quelle von der Bewertung dieser Aussage getrennt.[^13]

Der Grounded Vault ist unser Versuch, diese Zuordnung als Struktur anzulegen. Ein Repository führt archiviertes Quellmaterial in Markdown-Repräsentationen mit stabilen Blockankern, verdichtet jede Quelle zu einem Destillat aus einzeln adressierten Aussagen und synthetisiert daraus quellenübergreifende Assertions. Die tragenden Sätze des fertigen Texts verweisen per Fußnote auf diese Assertions, so wie es dieser Beitrag tut. Von jedem Satz führt damit eine maschinell auflösbare Ankerkette bis zur Fundstelle in der archivierten Quelle, und ein Skript prüft, ob jede Station dieser Kette existiert.[^12]

Neu ist an dieser Anlage weniger, als es scheint. Das Destillat ist das Exzerpt der geisteswissenschaftlichen Arbeitspraxis, eine Quelle, ausgewählte Aussagen, jede mit Fundstelle. Die Assertion-Schicht arbeitet wie Luhmanns Zettelkasten, dessen Karten über feste Nummern adressierbar sind und dessen Funktionieren an einer dichten Verweisstruktur zwischen ihnen hängt, eine unverlinkte Notiz geht dort unwiederbringlich verloren.[^6] Der Fußnotenvertrag des Endtexts folgt dem kritischen Apparat, wie ihn die TEI kodiert, jede Lesart wird über ein Attribut mit den Zeugen verknüpft, die sie bezeugen, und die Guidelines empfehlen für jeden Zeugen eine eindeutige Sigle und in der Regel ein Zeugenregister im Editionskopf.[^7] Die Methode setzt diese Praktiken unter agentische Bedingungen fort. Agenten führen die Arbeitsschritte aus, und Maschinen prüfen die Struktur.

Die Architektur unterscheidet dabei zwei Dinge, die leicht verschwimmen. Grounding ist die strukturelle Rückbindung, ein Anker, der auflöst. Ob die Fundstelle die Aussage trägt, ist eine eigene Prüfentscheidung, und ob die Aussage wahr ist, noch einmal eine andere. Das W3C-Provenienzmodell zieht dieselbe Grenze für sich selbst, die Validität eines Provenienz-Records ist dort interne Konsistenz, eine kohärente Historie, und Provenienz gilt als Grundlage für Vertrauensentscheidungen.[^8] Deshalb prüfen im Grounded Vault drei getrennte Instanzen. Die deterministische Validierung prüft Form und Auflösbarkeit der Anker. Ein adversariales LLM-Review prüft je Paar aus Aussage und Fundstelle, ob die Fundstelle trägt, mit fünf festen Verdikten, von denen nur die volle Stützung besteht. Die menschliche Verifikation entscheidet zuletzt, ob die vorgelegte Fundstelle als Evidenz akzeptiert wird, und nur sie darf den höchsten Status setzen.

Dass die maschinelle Prüfung nötig ist, zeigt schon der Aufbau dieses Bestands. LLM-Zusammenfassungen wissenschaftlicher Texte verbreitern den Geltungsbereich der Originalbefunde systematisch, und die Instruktion, Ungenauigkeiten zu vermeiden, verdoppelt diese Übergeneralisierung nahezu.[^9] Beim Bau der ersten zwanzig Assertions dieses Vaults fand das Review sechzehn solcher Verschiebungen, normative Empfehlungen waren als Praxis wiedergegeben, gepoolte Ergebnisse distributiv gelesen, Studiendesigns beschrieben, die keine Fundstelle trägt. Jede wurde vor der Publikation zurückgebaut.[^10]

Zwei Grenzen gehören in den Auftakt. Ein auflösbarer Anker garantiert Rückverfolgbarkeit. Über die Wahrheit der Quelle und die Qualität des fertigen Texts sagt er nichts, und ob die Methode die inhaltliche Qualität gegenüber unverankertem Schreiben hebt, wissen wir nicht.[^11] Die Provenienztiefe entsteht zudem nur, wenn die Quellen zum Verarbeitungszeitpunkt archiviert werden, nachträglich lässt sie sich kaum herstellen. Der zugrunde liegende Bestand ist öffentlich, und jede Fußnote dieses Texts löst in ihm auf. Die folgenden Beiträge entwickeln die Begriffe, die Prüfregeln, den realen Aufbau dieses Vaults und seine Werkzeuge.

[^1]: Grounded in [[30_assertions/generated-citations-often-fail-to-support-their-sentences]].
[^2]: Grounded in [[30_assertions/source-binding-lowers-unsupported-citation-without-eliminating-it]].
[^3]: Grounded in [[30_assertions/resolvable-citation-without-support-is-a-distinct-error-class]].
[^4]: Grounded in [[30_assertions/attribution-is-separate-from-correctness]].
[^5]: Grounded in [[30_assertions/historical-method-separates-origin-check-from-credibility]].
[^6]: Grounded in [[30_assertions/card-index-organizes-knowledge-as-addressable-linked-notes]].
[^7]: Grounded in [[30_assertions/critical-apparatus-binds-reading-to-witnesses]].
[^8]: Grounded in [[30_assertions/prov-validity-is-internal-consistency]].
[^9]: Grounded in [[30_assertions/llm-summaries-broaden-the-scope-of-findings]].
[^10]: Posit: Befund aus den Review-Protokollen dieser Instanz vom 2026-08-10. Open evidence question: die Review-Verdikte sind noch als data-Quelle zu ingestieren, damit diese Zählung selbst eine Fundstelle bekommt.
[^11]: Posit: eigene Einschätzung, ein kontrollierter Vergleich mit unverankert geschriebenen Texten ist uns nicht bekannt. Open evidence question: Gibt es einen solchen Vergleich, und wie wäre er anzulegen?
[^12]: Posit: Selbstbeschreibung der Architektur, festgelegt im Template-Repository dieser Instanz. Open evidence question: ein Ingest des Template-Repositoriums als document-Quelle würde diese Selbstbeschreibung anchorbar machen.
[^13]: Posit: eigene Zusammenschau von [^4] und [^5]. Keine der beiden Quellen stellt diesen Vergleich selbst an. Open evidence question: Gibt es wissenschaftsgeschichtliche Literatur, die die quellenkritische Zweistufigkeit und die Attributionsforschung aufeinander bezieht?
