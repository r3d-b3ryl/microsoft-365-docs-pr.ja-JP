---
title: Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)
description: 脅威が検出されると、これらの脅威に対応して軽減するためのアクションを実行できます。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365initiative-defender-business
ms.openlocfilehash: 16321f7941f44f599f3b1940bdbe56471a6d6311
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2022
ms.locfileid: "62244765"
---
# <a name="respond-to-and-mitigate-threats-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

このMicrosoft 365 Defenderを使用すると、セキュリティ チームは検出された脅威に対応し、軽減できます。 この記事では、Defender for Business (プレビュー) を使用する方法の例について説明します。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="view-detected-threats"></a>検出された脅威を表示する

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
