---
title: 攻撃シミュレーション トレーニングのペイロードの自動化
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
description: 管理者は、ペイロードオートメーション (ペイロードハーベスト) を使用して、Microsoft Defender for Office 365 プラン 2 での攻撃シミュレーショントレーニングの自動シミュレーションを収集および起動する方法について説明します。
ms.technology: mdo
ms.openlocfilehash: aa223ab1abda110e32a9b9dc55e9dc76a1983321
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468437"
---
# <a name="payload-automations-for-attack-simulation-training"></a>攻撃シミュレーション トレーニングのペイロードの自動化

**Microsoft Defender for** [Office 365プラン 2 に適用されます](defender-for-office-365.md)

Microsoft 365 E5 または Microsoft Defender for Office 365 Plan 2 の攻撃シミュレーション トレーニングでは、ペイロードの自動化 (ペイロードの _収集とも呼_ ばれる) は、組織内のユーザーによって報告された実際のフィッシング メッセージから情報を収集します。 組織ではこれらのメッセージの数が少ない可能性が高いが、フィッシング攻撃 (受信者、ソーシャル エンジニアリング手法、送信者情報など) で検索する条件を指定できます。 攻撃シミュレーショントレーニングは、攻撃で使用されるメッセージとペイロードを模倣して、ターゲットユーザーに対して無害なシミュレーションを自動的に開始します。

ペイロードの自動化を作成するには、次の手順を実行します。

1. [電子メール Microsoft 365 Defender] <https://security.microsoft.com/>ポータルの [電子メール &**攻撃** \> **シミュレーション トレーニング** \> **ペイロードの自動化] タブに移動** します。

   [ペイロードの自動化] タブ **に直接移動するには** 、 を使用します <https://security.microsoft.com/attacksimulator?viewid=payloadautomation>。

2. [ペイロードの **自動化] タブで、[** オートメーションの作成] ![アイコンを選択します。](../../media/m365-cc-sc-create-icon.png) **オートメーションを作成します**。

   :::image type="content" source="../../media/attack-sim-training-sim-automations-create.png" alt-text="[ペイロードの自動化] タブの [シミュレーションの作成] ボタンは、Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニング" lightbox="../../media/attack-sim-training-sim-automations-create.png":::

3. 作成ウィザードが開きます。 この記事の残りの部分では、ページとページに含まれる設定について説明します。

> [!NOTE]
> 作成ウィザードの任意の時点で、[保存して閉じる] をクリックして進行状況を保存し、後でペイロードオートメーションの構成を続行できます。 [ペイロードの自動化] タブで![ペイロードオートメーションを選択し、[オートメーションの編集] アイコンをクリックすると、移動先を選択できます。](../../media/m365-cc-sc-edit-icon.png) **オートメーションの編集**。

## <a name="automation-name"></a>オートメーション名

[オートメーション名 **] ページで** 、次の設定を構成します。

- **名前**: ペイロードオートメーションの一意でわかりやすい名前を入力します。
- **説明**: ペイロードの自動化に関するオプションの詳細な説明を入力します。

完了したら、**[次へ]** をクリックします。

## <a name="run-conditions"></a>条件の実行

[条件 **の実行] ページ** で、自動化の実行を決定する実際のフィッシング攻撃の条件を選択します。

各条件は 1 回のみ使用できます。 複数の条件で AND ロジック ( および ) を\<Condition1\> 使用します \<Condition2\>。

![条件アイコンを追加します。](../../media/m365-cc-sc-create-icon.png) **条件を追加します**。

- **違います。キャンペーンの対象ユーザー数**: 次の設定を構成します。
  - **等しい**、**より小さい****、より大きい**、**より小** さいか等しい、または **より大きいか等しい**。
  - **値を** 入力します。 フィッシング キャンペーンの対象となったユーザーの数。
- **特定のフィッシング手法を使用するキャンペーン**: 使用可能な値のいずれかを選択します。
  - **資格情報の取得**
  - **マルウェアの添付ファイル**
  - **添付ファイルのリンク**
  - **マルウェアへのリンク**
  - **ドライブバイ URL**
- **特定の送信者ドメイン**: 送信者のメール ドメイン値を入力します (たとえば、contoso.com)。
- **特定の送信者名**: 送信者名の値を入力します。
- **特定の送信者メール**: 送信者の電子メール アドレスを入力します。
- **特定のユーザーとグループの受信者**: ユーザーまたはグループの名前または電子メール アドレスの入力を開始します。 表示されたら、選択します。

条件を追加した後で削除するには、 ![[削除] アイコン](../../media/m365-cc-sc-delete-icon.png).

完了したら、**[次へ]** をクリックします。

## <a name="review-automation"></a>オートメーションの確認

[自動化 **の確認] ページ** で、ペイロードの自動化の詳細を確認できます。

各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

完了したら、**[送信]** をクリックします。
