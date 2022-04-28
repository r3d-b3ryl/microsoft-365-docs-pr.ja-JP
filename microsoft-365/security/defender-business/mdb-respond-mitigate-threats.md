---
title: Microsoft Defender for Businessの脅威に対応し、軽減する
description: 脅威が検出されると、それらの脅威に対応して軽減するためのアクションを実行できます。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 04/14/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: b6d85d5032b9eb5837482649d4164e68b7c08275
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65098782"
---
# <a name="respond-to-and-mitigate-threats-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessの脅威に対応し、軽減する

> [!NOTE]
> Microsoft Defender for Businessが[Microsoft 365 Business Premium](../../business-premium/index.md)に含まれるようになりました。 

Microsoft 365 Defender ポータルを使用すると、セキュリティ チームは検出された脅威に対応し、軽減できます。 この記事では、Defender for Business を使用する方法の例について説明します。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="view-detected-threats"></a>検出された脅威を表示する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ホーム ページのカードに注目してください。 カードでは、検出された脅威の数と、影響を受けたユーザー アカウント、エンドポイント (デバイス)、その他の資産の数が一目でわかります。 次の図は、表示される可能性があるカードの例です。

   :::image type="content" source="../../media/defender-business/mdb-examplecards.png" alt-text="Microsoft 365 Defender ポータルのカードのスクリーンショット":::

3. カードのボタンまたはリンクを選択して、詳細情報を表示し、アクションを実行します。 たとえば、 **リスクのあるデバイス** カードには 、[ **詳細の表示]** ボタンが含まれています。 このボタンを選択すると、次の図に示すように、[ **デバイス インベントリ]** ページに移動します。

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="デバイス インベントリのスクリーンショット":::

   **[デバイス インベントリ]** ページには、会社のデバイスとそのリスク レベルと露出レベルが一覧表示されます。

4. デバイスなどの項目を選択します。 ポップアップ ウィンドウが開き、次の図に示すように、そのアイテムに対して生成されたアラートとインシデントに関する詳細情報が表示されます。  

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout.png" alt-text="選択したデバイスのポップアップ ウィンドウのスクリーンショット":::

5. ポップアップで、表示される情報を表示します。 省略記号 (...) を選択して、次の図に示すように、使用可能なアクションを一覧表示するメニューを開きます。 

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout-menu.png" alt-text="選択したデバイスで使用可能なアクションのスクリーンショット":::

6. 使用可能なアクションを選択します。 たとえば、[**ウイルス対策スキャンの実行**] を選択すると、Microsoft Defender ウイルス対策デバイスでクイック スキャンが開始されます。 または、[ **自動調査の開始** ] を選択して、デバイスの自動調査をトリガーすることもできます。

## <a name="next-steps"></a>次の手順

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)
- [Microsoft Defender for Businessでデバイスを管理する](mdb-manage-devices.md)
- [Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)
