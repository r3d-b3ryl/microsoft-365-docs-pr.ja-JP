---
title: 攻撃シミュレーション トレーニングのペイロード自動化
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、ペイロードの自動化 (ペイロード の収集) を使用して、Microsoft Defender for Office 365プラン 2 で攻撃シミュレーション トレーニングの自動シミュレーションを収集して起動する方法を学習できます。
ms.technology: mdo
ms.openlocfilehash: 7fb3b0bbad5bbec8044a94da1943b0bd25eba865
ms.sourcegitcommit: 872ab0b6a225c20274916e07ed4cc4944be9509a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65679376"
---
# <a name="payload-automations-for-attack-simulation-training"></a>攻撃シミュレーション トレーニングのペイロード自動化

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

[Microsoft Defender for Office 365プラン 2](defender-for-office-365.md) **に適用されます**

Microsoft 365 E5またはMicrosoft Defender for Office 365計画 2 の攻撃シミュレーション トレーニングでは、ペイロードの自動化 (_ペイロード の収集_ とも呼ばれます) は、組織内のユーザーによって報告された実際のフィッシング メッセージから情報を収集します。 これらのメッセージの数は組織内では少ない可能性がありますが、フィッシング攻撃で検索する条件 (受信者、ソーシャル エンジニアリング手法、送信者情報など) を指定できます。 その後、攻撃シミュレーション トレーニングは、攻撃で使用されるメッセージとペイロードを模倣して、対象ユーザーに無害なシミュレーションを自動的に起動します。

ペイロードオートメーションを作成するには、次の手順に従います。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com/>[**電子メール & コラボレーション** \> **の攻撃シミュレーション トレーニング** \> **自動化**] タブの **[ペイロードの自動化**] タブに移動します\>。

   **[オートメーション]** タブに直接移動するには、 <https://security.microsoft.com/attacksimulator?viewid=automations>.

2. **ペイロードオートメーションで、[オートメーションの** 作成] アイコンを選択![します。](../../media/m365-cc-sc-create-icon.png) **自動化を作成します**。

   :::image type="content" source="../../media/attack-sim-training-sim-automations-create.png" alt-text="Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングの [ペイロードの自動化] タブの [シミュレーションの作成] ボタン" lightbox="../../media/attack-sim-training-sim-automations-create.png":::

3. 作成ウィザードが開きます。 この記事の残りの部分では、ページとそのページに含まれる設定について説明します。

> [!NOTE]
> 作成ウィザードの任意の時点で、[ **保存] をクリックして閉じて** 進行状況を保存し、後でペイロードオートメーションの構成を続行できます。 [ **Payload Automations**] でペイロードオートメーションを選択し、[オートメーションの編集] アイコンをクリック ![すると、中断した場所を選択できます。](../../media/m365-cc-sc-edit-icon.png) **オートメーションを編集します**。

## <a name="automation-name"></a>オートメーション名

[ **オートメーション名]** ページで、次の設定を構成します。

- **名前**: ペイロードオートメーションのわかりやすい一意の名前を入力します。
- **説明**: ペイロードの自動化に関するオプションの詳細な説明を入力します。

完了したら、**[次へ]** をクリックします。

## <a name="run-conditions"></a>実行条件

[ **実行条件** ] ページで、自動化をいつ実行するかを決定する実際のフィッシング攻撃の条件を選択します。

各条件は 1 回だけ使用できます。 複数の条件で AND ロジック (\<Condition1\> および \<Condition2\>) を使用します。

![[条件の追加] アイコン。](../../media/m365-cc-sc-create-icon.png) **条件を追加します**。

- **いいえ。キャンペーンの対象ユーザーの** 数: 次の設定を構成します。
  - **等しい**、 **より小さい**、 **より大きい**、 **より小さいか等しい** か、またはそれ **以上** です。
  - **値を入力** します。フィッシング キャンペーンの対象となったユーザーの数。
- **特定のフィッシング手法を使用したキャンペーン**: 使用可能な値のいずれかを選択します。
  - **資格情報の収集**
  - **マルウェアの添付ファイル**
  - **添付ファイル内のリンク**
  - **マルウェアへのリンク**
  - **ドライブバイ URL**
- **特定の送信者ドメイン**: 送信者の電子メール ドメインの値 (contoso.com など) を入力します。
- **特定の送信者名**: 送信者名の値を入力します。
- **特定の送信者の電子メール**: 送信者の電子メール アドレスを入力します。
- **特定のユーザーとグループの受信者**: ユーザーまたはグループの名前または電子メール アドレスの入力を開始します。 表示されたら、選択します。

条件を追加した後で削除するには、 ![[削除] アイコン](../../media/m365-cc-sc-delete-icon.png).

完了したら、**[次へ]** をクリックします。

## <a name="review-automation"></a>自動化を確認する

[ **オートメーションの確認** ] ページで、ペイロードの自動化の詳細を確認できます。

各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

完了したら、**[送信]** をクリックします。
