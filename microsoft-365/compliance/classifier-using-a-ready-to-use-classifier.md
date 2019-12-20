---
title: すぐに使用できる分類子を使用する (プレビュー)
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
description: Microsoft 365 には、組織全体でコンテンツを識別してラベルを付けるために使用できる、machine learning 分類子を使用するための準備が整ったことが用意されています。 このトピックでは、これらを使用して分類子を使用する準備をする方法について説明します。
ms.openlocfilehash: 6eaa3689dce1bfb37fdad6b1b22dcac3539bb31e
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807416"
---
# <a name="using-a-ready-to-use-classifier-preview"></a>すぐに使用できる分類子を使用する (プレビュー)

Microsoft では、非常に大規模なサンプルデータセットを使用して多数の分類子をトレーニングおよびテストしており、特定のカテゴリのコンテンツを特定するのに役立ちます。 「 [Trainable 分類子の概要 (プレビュー)」を](classifier-getting-started-with.md)参照してください。 既定では、 `Ready to use`これらの分類子はグループに表示されます。

- **不快な言葉**: profanities、slurs、taunts、および偽装式を含むテキストアイテムを検出します (これは、より不快な用語と同じ意味を持つ式です)。
- **履歴書**: 申請者の個人、教育、専門資格、作業経験、その他の個人を特定できる情報のテキストアカウントであるアイテムを検出します。
- **SourceCode**: 広く使用されているコンピュータプログラミング言語で記述された命令およびステートメントのセットを含むアイテムを検出します。
- **嫌がらせ**: 次の特徴に基づいて、1人または複数の個人を対象とした不快感のある言語のテキストアイテムの特定のカテゴリを検出します。競合、ethnicity、宗教、国内原産者、性別、性的なオリエンテーション、年齢、障碍。
- **不適切な用語**: 多くの人々を embarrass する式を含む、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。
- **脅威**: 暴力をコミットする脅威、または人またはプロパティに物理的な危害または損傷を与える脅威に関連する、不快感を与える言語のテキストアイテムの特定のカテゴリを検出します。

> [!NOTE]
> 分類とラベル付けワークフローで分類子を使用できるようにするには、事前に組織のコンテンツのサンプルに照らしてテストし、分類の予測が期待どおりに満たされることを確認する必要があります。

> [!IMPORTANT]
> 不快な言葉、嫌がらせ、冒涜、および脅威の分類子は、検索可能なテキストのみで機能することに注意してください。 さらに、言語と文化的な標準が絶えず変化し、これらの現実からは、これらの分類子を裁量で更新する権利を Microsoft が留保します。 分類子は、お客様の組織が不快な言葉や使用されている他の言語を監視するのに役立ちますが、分類子は、そのような言語の結果に対応していません。そのような言語。 お客様の組織は、Microsoft またはその子会社ではなく、事前に訓練された分類子によって識別されるコンテンツの監視、実施、ブロック、削除、保持に関連するすべての意思決定に対して責任を負うことになります。

## <a name="how-to-prepare-for-and-use-a-ready-to-use-classifier"></a>使用準備の分類子を準備して使用する方法

1. 破棄可能なテストコンテンツ項目を収集します。 [使用準備完了] 分類子 (正の一致) とそのカテゴリに含まれていないもの (負の一致) のカテゴリに属していると考えられます。

> [!IMPORTANT]
> サンプルアイテムは、暗号化する必要がなく、英語でなければなりません。

2. 専用の SharePoint Online フォルダーを作成します。フォルダーが検索インデックスに追加されるまで、少なくとも1時間待機します。 フォルダーの URL をメモしておきます。

3. コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター**または**microsoft 365 セキュリティセンター** > の**レコード管理 (プレビュー)** > **ラベルポリシー**タブを開きます。

4. [ `Auto-apply a label`] を選択します。

5. [ `Choose a label to auto-apply`] を選択します。

6. この`Create new labels`テストで使用するラベルを選択して作成します。 この操作を行う場合は`Retention` 、[オフ] のままにします。 保持またはその他のアクションをオンにしない。 この場合は、アクションを強制しないで、単にテキストラベルとして保持ラベルを使用します。 たとえば、アクションなしで「SourceCode クラシファイア test」という名前の保持ラベルを作成し、その保持ラベルを条件としてソースコード分類子のコンテンツに自動適用することができます。 保持ラベルの作成の詳細については、「[保持ラベルの概要](labels.md)」を参照してください。
  
7. [ `Auto-apply a label` ] を`Choose a label to auto-apply`選択してから、を選びます。 条件に基づいてラベルを自動適用する方法の詳細については、「[条件に基づいて保持ラベルポリシーを自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)する」を参照してください。

8. リストからテストラベルを選択し、を`Next`選択します。

9. [ `Apply label to content that matches a trainable classifier`] を選択します。

![分類子を条件として選択する](media/classifier-pre-trained-apply-label-match-trainable-classifier.png).

10. この場合は、リストから分類子を選択します。`Source Code`

11. ポリシーに名前を指定します。たとえば、"ソースコードの準備のために、クラシファイアテストを使用するようにします" などです。

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
- [保持ラベルの概要](labels.md)
- [条件に基づいて保持ラベルポリシーを自動適用する](labels.md#applying-a-retention-label-automatically-based-on-conditions)
