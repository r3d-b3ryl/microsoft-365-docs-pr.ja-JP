---
title: 組み込みの分類子を使用する (プレビュー)
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
ms.openlocfilehash: 2bd36ac42278cfe7b015d03caf2d9e1958908f8f
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193505"
---
# <a name="using-a-built-in-classifier-preview"></a>組み込みの分類子を使用する (プレビュー)

Microsoft では、非常に大規模なサンプルデータセットを使用して5つの分類子をトレーニングおよびテストしており、特定のカテゴリのコンテンツを特定するのに役立ちます。 「 [Trainable 分類子の概要 (プレビュー)」を](classifier-getting-started-with.md)参照してください。 既定では、 `Ready to use`これらの分類子はグループに表示されます。

Microsoft 365 には、推奨されている5つの組み込み分類子が付属しています。

> [!CAUTION]
> 誤検知が大量に発生しているため、**不快感**を持つ言語の組み込みの分類子を廃止しています。 使用しないでください。現在使用している場合は、ビジネスプロセスを移行する必要があります。 代わりに、**脅威**、**プロファニティ**、および**嫌がらせ**の組み込みの分類子を使用することをお勧めします。

- **履歴書**: 申請者の個人、教育、専門資格、作業経験、その他の個人を特定できる情報のテキストアカウントであるアイテムを検出します。
- **ソースコード**: GitHub で使用されている上位25台のコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。

|言語名|||||
|---------|---------|---------|---------|---------|
|『|C        |40u-c#       |+     |Clojure  |
|CoffeeScript|CSS     |移動       |Haskell |HTML     |
|Java     |JavaScript|Lua      |MATLAB   |Objective-C|
|Perl     |PHP      |Python   |R        |Ruby     |
|スケール a    |Shell    |実現    |テックス      |Vim スクリプト|

- **嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感のある言語のテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍。
- **不適切な用語**: 多くの人々を embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。
- **脅威**: 暴力をコミットする脅威、または人またはプロパティに物理的な危害または損傷を与える脅威に関連する、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。

> [!NOTE]
> 分類とラベル付けワークフローに組み込み分類子を使用する前に、組織のコンテンツのサンプルに照らしてテストし、分類の予測が期待どおりに満たされることを確認する必要があります。

> [!IMPORTANT]
> 不快な言葉、嫌がらせ、冒涜、および脅威の分類子は、検索可能なテキストのみで機能することに注意してください。 さらに、言語と文化的な標準が絶えず変化し、これらの現実からは、これらの分類子を裁量で更新する権利を Microsoft が留保します。 分類子は、お客様の組織に不快な言葉や使用されている言語の監視を支援することがありますが、分類子はそのような言語の影響を受けません。また、そのような言語の使用を監視したり、それに応答したりすることを意図したものではありません。 お客様の組織は、Microsoft またはその子会社ではなく、事前に訓練された分類子によって識別されるコンテンツの監視、実施、ブロック、削除、保持に関連するすべての意思決定に対して責任を負うことになります。

## <a name="how-to-prepare-for-and-use-a-built-in-classifier"></a>組み込みの分類子を準備して使用する方法

1. 組み込みの分類子のカテゴリに属していると考えられる (正の一致)、または、テストするカテゴリに含まれるべきではないものを含む、破棄可能なテストコンテンツ項目を収集します。

> [!IMPORTANT]
> サンプルアイテムは、暗号化する必要がなく、英語でなければなりません。

2. 専用の SharePoint Online フォルダーを作成します。フォルダーが検索インデックスに追加されるまで、少なくとも1時間待機します。 フォルダーの URL をメモしておきます。

3. コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター** > の**レコード管理 (プレビュー)** > **ラベルポリシー**タブを開きます。

4. [ `Auto-apply a label`] を選択します。

5. [ `Choose a label to auto-apply`] を選択します。

6. この`Create new labels`テストで使用するラベルを選択して作成します。 この操作を行う場合は`Retention` 、[オフ] のままにします。 保持またはその他のアクションをオンにしない。 この場合は、アクションを強制しないで、単にテキストラベルとして保持ラベルを使用します。 たとえば、アクションなしで「SourceCode クラシファイア test」という名前の保持ラベルを作成し、その保持ラベルを条件としてソースコード分類子のコンテンツに自動適用することができます。 保持ラベルの作成の詳細については、「[保持ラベルの概要](labels.md)」を参照してください。
  
7. [ `Auto-apply a label` ] を`Choose a label to auto-apply`選択してから、を選びます。 条件に基づいてラベルを自動適用する方法の詳細については、「[条件に基づいて保持ラベルポリシーを自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)する」を参照してください。

8. リストからテストラベルを選択し、を`Next`選択します。

9. [ `Apply label to content that matches a trainable classifier`] を選択します。

![分類子を条件として選択する](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png).

10. この場合は、リストから分類子を選択します。`Source Code`

11. ポリシーに名前を指定します。たとえば、"ソースコードの組み込みの分類子テスト" のようにします。

12. [ `Let me choose specific locations`] を選択します。

13. を除く`SharePoint sites`すべての場所をオフ`Choose sites`にします。

14. 手順2でサイトの URL を入力します。

15. ウィザードを終了し、`Auto-apply`

16. テストアイテムを専用の SharePoint Online フォルダーに配置します。

17. ラベルが適用される時間を有効にします。

18. ラベルのドキュメントのプロパティをチェックして、分類子が予期したとおりにテストコンテンツを含むかどうかを確認します。

19. ラベル付けされたアイテムを確認します。

20. テストを完了したら、コンテンツとラベルポリシーを削除します。

関連項目:

- [トレーニング可能な分類子の使用を開始する (プレビュー)](classifier-getting-started-with.md)
- 「[保持ラベルの概要](labels.md)」を参照してください。
- [条件に基づいて保持ラベルポリシーを自動適用する](labels.md#applying-a-retention-label-automatically-based-on-conditions)
