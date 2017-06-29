# Recommending and Localizing Change Requests for Mobile Apps based on User Reviews

変更伝播は、主に保守履歴またはソースコード分析によって推定されています。しかし、履歴やコードにアクセスできない場合や、異機種ソースなどの分析に非現実的な場合があります。以前は、ドメインレベルのコンポーネントを変更することによる変化の伝播は、純粋にドメインユーザーが利用できる情報から予測できると仮定しました。我々は、ドメインベースの変化伝播解析を提案し、アナリストとドメインの専門家が実装とは独立した概念的な結合を予測できるようにした。本稿では、重要な（エンタープライズ）システムへのドメインベースの分析の適用について報告します。ドメインベースの分析とよく知られた履歴ベースの分析の両方を行い、結果を比較しました。ヒストリベースのアプローチと同様に、ドメインベースの分析により、ソフトウェアコンポーネント間の結合が明らかになり、ソフトウェアメンテナンスのエラーを防止し、変化の伝播を予測するのに役立ちます。確立されたアプローチが非実用的であると考えられる特定の種類のシステムに適用する価値があると結論づける。

## Change Advisor
* Parse Source Code to Code Compornent(like Class)
* Extract word in Class

1) user feedback identification and classification (i.e., bug fixing tasks, features enhancement, and new features requests);
2) source code and user feedback preprocessing; 3) user feedback clustering, representing similar user needs (i.e., code change requests);
4) determining the code artifacts related to the suggested software changes.
<!--1）ユーザフィードバックの識別および分類（すなわち、バグ修正タスク、機能拡張、および新機能要求）。
2）ソースコードとユーザフィードバックの前処理。 
3）同様のユーザニーズ（すなわち、コード変更要求）を表すユーザフィードバッククラスタリング。
4）提案されたソフトウェア変更に関連するコードアーチファクトを決定する。-->

---

* RQ1: Does CHANGEADVISOR identify cohesive user feedback clusters representing related change requests?
* RQ2: Does CHANGEADVISOR correctly link change requests represented by user feedback clusters to code artifacts that need to be modified and how well it works compared to a state-of-the-art technique relating informal textual documentation to source code?
* RQ3:Are the suggestions provided by ChangeAdvisor actually useful for developers?
<!--•RQ1：CHANGEADVISORは、関連する変更要求を表す一貫性のあるユーザーフィードバッククラスタを識別しますか？
•RQ2：CHANGEADVISORは、ユーザーフィードバッククラスターによって表される変更要求を、変更する必要があるコード成果物に正しくリンクするか、インフォーマルなテキスト文書をソースコードに関連付ける最先端の技術と比較してどれくらいうまく機能しますか？
* 提案が有益であったか？
-->

---

### RQ1: Does CHANGEADVISOR identify cohesive user feedback clusters representing related change requests?
They asked the experts to rate the cohesiveness of clusters using a Likert scale(five-level) 5+ years experience()

Median = 4(Agree)
Max = 5(Strongly agree)

<!--リッカート尺度
全く同意できない
同意できない
どちらともいえない
同意できる
非常に同意できる-->

---

### RQ2: Does CHANGEADVISOR correctly link change requests represented by user feedback clusters to code artifacts that need to be modified and how well it works compared to a state-of-the-art technique relating informal textual documentation to source code?
####Compare BLUiR

* ChangeAdvisor
    * Precision:81%
    * Recall:70%
* BLUiR
    * Precision:34%
    * Recall:32%

---

```
* ChangeAdvisor
    * Precision:81%
    * Recall:70%
* BLUiR
    * Precision:34%
    * Recall:32%
```
@[5](ただしBLUiRの34%のうち5%はChangeAdvisorがサポートしていない)

---

#### RQ3:Are the suggestions provided by ChangeAdvisor actually useful for developers?
How well are the user reviews grouped according to the number of source code components that need to be modiﬁed? Precision. How well do the proposed classes match the actual set of those needed to be changed in order to satisfy the user requests? Completeness. Evaluate the completeness of the set of classes suggested compared to the actual set of those needed to be modiﬁed
<!--
変更が必要なソースコードコンポーネントの数に応じてユーザーのレビューをグループ分けしてもよいでしょうか？ 精度。 提案されたクラスは、ユーザー要求を満たすために変更する必要があるクラスの実際のセットとどれくらいうまく一致しますか？ 完全。 提案された一連のクラスの完全性を、修正が必要な実際のセットと比較して評価する-->

I know what changes I have to make in my app when implementing a change. However, a tool like this may help in quantifying the number of classes to be modiﬁed.

<!--私は変更を実装するときに私のアプリケーションで何をしなければならないのか分かっています。 しかし、このようなツールは、変更するクラスの数を数量化する際に役立ちます。-->


* it is more accurate than a state-of-the-art technique developed in the context of bug localization [21]. The study conducted with the original developers of the apps in our dataset confirmed the usefulness of our approach in practice
<!--
バグのローカライゼーションの文脈で開発された最先端の技術よりも正確です[21]。 私たちのデータセットのアプリのオリジナル開発者と一緒に実施されたこの調査は、実際のアプローチの有用性を確認しました-->