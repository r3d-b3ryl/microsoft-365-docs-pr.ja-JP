---
title: 保持ラベルを使用した組み込み分類子のテスト (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 には、組織全体でコンテンツを識別してラベルを付けるために使用できる組み込みの分類子がいくつか用意されています。 このトピックでは、これらの分類子の使用を準備する方法について説明します。
ms.openlocfilehash: 1d645cc79075c41ce94b0f9b4fc347450a8df8c6
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146221"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a>保持ラベルを使用した組み込み分類子のテスト (プレビュー)

Microsoft では、特定のカテゴリのコンテンツを特定するのに役立つ5つの分類子をトレーニングおよびテストしています。 これらの分類子は、 `Ready to use` 既定でグループに表示され、非常に大きなサンプルデータセットを使用してトレーニングされています。

> [!IMPORTANT]
> 分類とラベル付けワークフローに組み込み分類子を使用する前に、組織のコンテンツのサンプルに照らしてテストし、分類の予測が期待どおりに満たされることを確認する必要があります。

Trainable 分類子の詳細については、「 [trainable 分類子の概要 (プレビュー)](classifier-getting-started-with.md)」を参照してください。

Microsoft 365 には、推奨される 5 つの組み込み分類子が付属しています。

> [!CAUTION]
> 組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。 使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。 代わりに、[**脅威**]、[**冒涜的表現**]、および [**ハラスメント**] の組み込み分類子を使用することをお勧めします。

- **履歴書**: 申請者の個人、教育、専門資格、作業経験、その他個人を識別する情報のテキストアカウントであるアイテムを検出します。
- **ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。

  |**言語名**|||||
  |---------|---------|---------|---------|---------|
  |ActionScript|C        |C#       |C++     |Clojure  |
  |CoffeeScript|CSS     |Go       |Haskell |HTML     |
  |Java     |JavaScript|Lua      |MATLAB   |Objective-C|
  |Perl     |PHP      |Python   |R        |Ruby     |
  |Scala    |Shell    |Swift    |Tex      |Vim Script|

> [!NOTE]
> ソースコードは、テキストの大部分がソースコードであるときに検出するためにトレーニングされています。 プレーンテキストが混在しているソースコードテキストは検出されません。

- **嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感を持つ、不快感を持つテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍
- **不適切な用語**: 多くのユーザーを embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。
- **脅威**: 暴力を確定する脅威、または人またはプロパティに物理的な悪影響や損害を与えることに関連する脅威に関連する、不快な言語のテキストアイテムの特定のカテゴリを検出します。

> [!IMPORTANT]
> 不快な言葉、ハラスメント、冒涜的表現、および脅威の分類は、検索可能なテキストでのみ機能し、網羅的または完全ではないことに注意してください。 さらに、言語と文化の基準は絶えず変化し、これらの現実に照らして、Microsoft は独自の裁量でこれらの分類子を更新する権利を留保します。 分類子は、不快な言語やその他の使用言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対処するものではなく、そのような言語の使用を監視または応答する唯一の手段を組織に提供するものではありません。 事前にトレーニングされた分類子によって識別されたコンテンツの監視、施行、ブロック、削除、および保持に関するすべての決定は、Microsoft またはその子会社ではなく、お客様の組織の責任となります。

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a>組み込みの分類子がニーズを満たすことを確認する方法

1. 組み込みの分類子のカテゴリに属していると考えられる (正の一致)、または、テストするカテゴリに含まれるべきではないものを含む、破棄可能なテストコンテンツ項目を収集します。

   > [!IMPORTANT]
   > サンプルアイテムは、暗号化する必要がなく、英語でなければなりません。

2. 専用の SharePoint Online フォルダーを作成します。フォルダーが検索インデックスに追加されるまで、少なくとも1時間待機します。 フォルダーの URL をメモしておきます。

3. コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター**の  >  **レコード管理 (プレビュー)**  >  **ラベルポリシー**タブを開きます。

4. [] を選択 `Auto-apply a label` します。

5. [] を選択 `Choose a label to auto-apply` します。

6. `Create new labels`このテストで使用するラベルを選択して作成します。 その場合は、 `Retention` をに設定 `off` します。 保持またはその他のアクションをオンにしない。 この場合は、アクションを強制しないで、単にテキストラベルとして保持ラベルを使用します。 たとえば、アクションなしで「SourceCode クラシファイア test」という名前の保持ラベルを作成し、その保持ラベルを条件としてソースコード分類子のコンテンツに自動適用することができます。 保持ラベルの詳細については、「[アイテム保持ポリシーと保持ラベルについ](retention.md)て」を参照してください。
  
7. [] を選択し `Auto-apply a label` てから、を選び `Choose a label to auto-apply` ます。 条件に基づいてラベルを自動適用する方法の詳細については、「[自動適用保持ラベルの条件を構成](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)する」を参照してください。

8. リストからテストラベルを選択し、を選択し `Next` ます。

9. [] を選択 `Apply label to content that matches a trainable classifier` します。

   ![分類子を条件として選択する](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

10. この場合は、リストから分類子を選択します。`Source Code`

11. ポリシーに名前を指定します。たとえば、"ソースコードの組み込みの分類子テスト" のようにします。

12. [] を選択 `Let me choose specific locations` します。

13. を除くすべての場所をオフにし `SharePoint sites` `Choose sites` ます。

14. 手順2でサイトの URL を入力します。

15. ウィザードを終了し、`Auto-apply`

16. テストアイテムを専用の SharePoint Online フォルダーに配置します。

17. ラベルが適用される時間を有効にします。

18. ラベルのドキュメントのプロパティをチェックして、分類子が予期したとおりにテストコンテンツを含むかどうかを確認します。

19. ラベル付けされたアイテムを確認します。

20. テストを完了したら、コンテンツとラベルポリシーを削除します。

関連項目:

- [トレーニング可能な分類子の使用を開始する (プレビュー)](classifier-getting-started-with.md)
- [アイテム保持ポリシーと保持ラベルについて](retention.md)
- [保持ラベルを自動的に適用してコンテンツを保持または削除する](apply-retention-labels-automatically.md)
