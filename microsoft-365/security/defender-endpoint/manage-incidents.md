---
title: エンドポイント インシデントの Microsoft Defender の管理
description: インシデントの割り当て、状態の更新、または分類の設定によってインシデントを管理します。
keywords: インシデント、管理、割り当て、状態、分類、真のアラート、誤ったアラート
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a84f7ba72acb4caf3e229f0bed4d997e123cc7ae
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466215"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>エンドポイント インシデントの Microsoft Defender の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

インシデントの管理は、すべてのサイバーセキュリティ操作の重要な部分です。 インシデントを管理するには、[インシデント] キューまたは [インシデント管理] ウィンドウからインシデント **を選択します**。 


インシデント キューからインシデントを選択すると、[インシデント管理] ウィンドウが表示されます。インシデントの詳細については、インシデント ページを開きます。

:::image type="content" source="images/atp-incidents-mgt-pane-updated.png" alt-text="インシデント管理ウィンドウ" lightbox="images/atp-incidents-mgt-pane-updated.png":::

インシデントを自分に割り当て、ステータスと分類を変更したり、名前を変更したり、コメントを付け、進捗状況を追跡することができます。

> [!TIP]
> 一目で見たインシデント名は、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいて自動的に生成されます。 これにより、インシデントの範囲をすばやく把握できます。
>
> たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*
>
> 自動インシデント名前付けのロールアウトの前に存在していたインシデントは、その名前を保持します。
>

:::image type="content" source="images/atp-incident-details-updated.png" alt-text="インシデントの詳細ページ" lightbox="images/atp-incident-details-updated.png":::

## <a name="assign-incidents"></a>インシデントを割り当てる
インシデントがまだ割り当てられていない場合は、[自分に割り当てる] を選択して、インシデントを自分に割り当てることができます。 これにより、インシデントの所有権だけでなくそのインシデントと関連するすべての警告の所有権が自分に割り当てられます。

## <a name="set-status-and-classification"></a>状態と分類を設定する
### <a name="incident-status"></a>インシデントの状態
インシデントは、調査の進捗に合わせて状態を変更することにより、**Active (アクティブ)** または **Resolved (解決済み)** に分類できます。 こうすることで、チームでのインシデントへの対応方法を整理して管理できます。

たとえば、SoC アナリストは、その日の緊急 **の** アクティブ インシデントを確認し、調査のために自分に割り当てました。

または、インシデントが修復された場合、SoC アナリストがインシデントを **解決** 済みとして設定する場合もあります。 

### <a name="classification"></a>分類
分類を設定しないことも、インシデントが真または偽であると指定することもできます。 こうすることで、チームにはインシデントの傾向が示され、チームの学習につながります。

### <a name="add-comments"></a>コメントを追加する
警告にはコメントを追加することができ、インシデントに関する過去のイベントを表示して、以前に行われた変更を確認できます。

警告に変更またはコメントが加えられるたびに、[Comments and history (コメントと履歴)] セクションに記録されます。

追加されたコメントは直ちにウィンドウに表示されます。



## <a name="related-topics"></a>関連項目
- [インシデント キュー](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [インシデント キューを表示および整理する](view-incidents-queue.md)
- [インシデントの調査](investigate-incidents.md)
