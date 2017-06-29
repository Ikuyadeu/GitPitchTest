## Recommending and Localizing Change Requests for Mobile Apps based on User Reviews
Palomba, Fabio
Salza, Pasquale
Ciurumelea, Adelina
Panichella, Sebastiano
Gall, Harald
Ferrucci, Filomena
Lucia, Andrea De

<!--研究者は、
モバイルアプリの維持と発展に役立つユーザーレビューから情報を抽出します。ただし、ほとんどのユーザーは、特定のキーワード（バグ、機能など）に基づいてユーザーレビューを自動的に分類するだけです。さらに、ユーザのフィードバックを変更するソースコードコンポーネントにリンクするためのサポートを提供していないため、手作業で時間がかかり、エラーを起こしやすいタスクが必要です。本稿では、ユーザレビューに含まれる文章の構造、意味、感情を分析して、メンテナンスの観点から有用な（ユーザの）フィードバックを抽出し、開発者にソフトウェア成果物の変更を推奨する新しいアプローチであるCHANGEADVISORを紹介する。それは自然言語処理とクラスタリングアルゴリズムに依存して、同様のユーザーのニーズや変更の提案に関するユーザーレビューをグループ化します。次に、テキストベースの発見的手法を使用して、推奨されるソフトウェアの変更に従って保守が必要なコード成果物を決定します。 10のオープンソースモバイルアプリとその元の開発者の44683人のユーザーレビューで行われた定量的および定性的な調査では、（i）同様のユーザー変更要求をクラスタリングし、（ii）影響を受けたコードコンポーネントを特定することでCHANGEADVISOR提案された変更。さらに、得られた結果は、CHANGEADVISORが、ユーザフィードバッククラスタをソースコードにリンクするベースラインアプローチよりも正確であることを示しています-->

---

## Change Advisor
1. user feedback identification and classification (i.e., bug fixing tasks, features enhancement, and new features requests);
2. source code and user feedback preprocessing; 
3. user feedback clustering, representing similar user needs (i.e., code change requests);
4. determining the code artifacts related to the suggested software changes.

<!--1）ユーザフィードバックの識別および分類（すなわち、バグ修正タスク、機能拡張、および新機能要求）。
2）ソースコードとユーザフィードバックの前処理。 
3）同様のユーザニーズ（すなわち、コード変更要求）を表すユーザフィードバッククラスタリング。
4）提案されたソフトウェア変更に関連するコードアーチファクトを決定する。-->

---
* Source code
    * Parse Source Code to Code Compornent(like Class)
    * Extract word in Class
* FeedBack
    * Classified by ARdoc(App Reviews Development Oriented Classifier)
    * Grouping similar user needs by HDP-LDA
---

* RQ1: Does CHANGEADVISOR identify cohesive user feedback clusters representing related change requests?
* RQ2: Does CHANGEADVISOR correctly link change requests represented by user feedback clusters to code artifacts that need to be modified and how well it works compared to a state-of-the-art technique relating informal textual documentation to source code?
* RQ3:Are the suggestions provided by ChangeAdvisor actually useful for developers?

<!-- RQ1：CHANGEADVISORは、関連する変更要求を表す一貫性のあるユーザーフィードバッククラスタを識別しますか？
•RQ2：CHANGEADVISORは、ユーザーフィードバッククラスターによって表される変更要求を、変更する必要があるコード成果物に正しくリンクするか、インフォーマルなテキスト文書をソースコードに関連付ける最先端の技術と比較してどれくらいうまく機能しますか？
* 提案が有益であったか？
-->

---

### Target
* 10 OSS mobile apps
* 44683 Usr Review

---

### RQ1: Does CHANGEADVISOR identify cohesive user feedback clusters representing related change requests?
They asked the experts to rate the cohesiveness of clusters using a Likert scale(five-level) 5+ years experience()

* Median = 4(Agree)
* Max = 5(Strongly agree)

<!--リッカート尺度
全く同意できない
同意できない
どちらともいえない
同意できる
非常に同意できる-->

---

##### RQ2: Does CHANGEADVISOR correctly link change requests represented by user feedback clusters to code artifacts that need to be modified and how well it works compared to a state-of-the-art technique relating informal textual documentation to source code?

Comparison between ChangeAdvisor and "BLUiR"

---
#### Comparison between ChangeAdvisor and BLUiR
```
* ChangeAdvisor
    * Precision:81%
    * Recall:70%
* BLUiR
    * Precision:34%
    * Recall:32%
```
@[5](But BLUiR 5 from Precision 34% is not supported  by ChangeAdvisor)

---

#### RQ3:Are the suggestions provided by ChangeAdvisor actually useful for developers?

* “I know what changes I have to make in my app when implementing a change. However, a tool like this may help in quantifying the number of classes to be modified.”
* “It would be useful for letting me immediately know to what extent a change is complicated to apply.”

---
#### Threats to Validity Threats

* Likert scale reflect a subjective perception of the problem.