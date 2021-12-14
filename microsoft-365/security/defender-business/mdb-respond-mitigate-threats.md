---
title: Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)
description: 脅威が検出されると、これらの脅威に対応して軽減するためのアクションを実行できます。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: cbd05b701c5276644e98671c9f07b4fbcf27c682
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421128"
---
# <a name="respond-to-and-mitigate-threats-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Microsoft Defender for Business (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

このMicrosoft 365 Defenderを使用すると、セキュリティ チームは検出された脅威に対応し、軽減できます。

1. ポータル ( ) にMicrosoft 365 Defenderサインイン [https://security.microsoft.com](https://security.microsoft.com) します。

2. [ホーム] ページのカードに注意してください。 カードは、検出された脅威の数と、影響を受けたユーザー アカウント、エンドポイント (デバイス)、その他のアセットの数を一目で示します。 次の図は、表示されるカードの例です。

   :::image type="content" source="../../media/defender-business/mdb-examplecards.png" alt-text="ポータル内のカードMicrosoft 365 Defenderスクリーンショット":::

3. カードのボタンまたはリンクを選択して、詳細を表示し、アクションを実行します。 たとえば、リスク カードに **[詳細の表示** ] ボタン **が含** まれています。 次の図に示すように、その **ボタンを** 選択すると、[デバイス インベントリ] ページに移動します。

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="デバイス インベントリのスクリーンショット":::

   [ **デバイス インベントリ] ページ** には、リスク レベルと露出レベルと共に、会社のデバイスが一覧表示されます。

4. デバイスなどのアイテムを選択します。 次の図に示すように、フライアウト ウィンドウが開き、そのアイテムに対して生成されたアラートとインシデントに関する詳細が表示されます。  

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout.png" alt-text="選択したデバイスのフライアウト ウィンドウのスクリーンショット":::

5. フライアウトで、表示される情報を表示します。 省略記号 (...)を選択して、次の図に示すように、使用可能なアクションを一覧表示するメニューを開きます。 

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout-menu.png" alt-text="選択したデバイスで使用可能なアクションのスクリーンショット":::

6. 使用可能なアクションを選択します。 たとえば、[ウイルス対策スキャンの **実行**] を選択すると、Microsoft Defender ウイルス対策クイック スキャンが開始されます。 または、[自動調査の **開始] を選択** して、デバイスで自動調査をトリガーすることもできます。

## <a name="next-steps"></a>次の手順

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)

- [Microsoft Defender for Business でデバイスを管理する (プレビュー)](mdb-manage-devices.md)

- [Microsoft Defender for Business でのインシデントの表示と管理 (プレビュー)](mdb-view-manage-incidents.md)
