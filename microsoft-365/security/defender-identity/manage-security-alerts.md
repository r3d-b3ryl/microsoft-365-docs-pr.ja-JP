---
title: Microsoft 365 Defenderでセキュリティ アラートをMicrosoft Defender for Identityする
description: Microsoft 365 DefenderでMicrosoft Defender for Identityによって発行されたセキュリティ アラートを管理および確認する方法について説明します
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: 3023dc05550aeee5a9d47bb7561eb221c6d1c588
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465819"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Microsoft 365 Defenderの Defender for Identity セキュリティ アラート

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、[Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center)で[Microsoft Defender for Identity](/defender-for-identity)セキュリティ アラートを操作する方法の基本について説明します。

Defender for Identity アラートは、専用の ID アラート ページ形式<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">でMicrosoft 365 Defender</a>にネイティブに統合されます。 これは、[Microsoft 365 Defenderに完全なMicrosoft Defender for Identityエクスペリエンスを導入](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)するための最初のステップです。

新しい ID アラート ページでは、Microsoft Defender for Identityお客様により優れたクロスドメインシグナルエンリッチメントと新しい自動 ID 応答機能が提供されます。 これにより、セキュリティが確保され、セキュリティ操作の効率が向上します。

[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)を通じてアラートを調査する利点の 1 つは、Microsoft Defender for Identityアラートがスイート内の他の各製品から取得した情報とさらに関連付けられる点です。 これらの強化されたアラートは、Microsoft Defender for Office 365とMicrosoft Defender for Endpointから発生する他の[Microsoft 365 Defender](/microsoft-365/security/office-365-security)アラート形式と一致[します](/microsoft-365/security/defender-endpoint)。 新しいページでは、ID に関連付けられたアラートを調査するために別の製品ポータルに移動する必要が実質的になくなります。

Defender for Identity から発信されたアラートは、アラートを自動的に修復したり、疑わしいアクティビティに貢献するツールやプロセスの軽減策など、Microsoft 365 Defender[自動調査と応答 (AIR)](/microsoft-365/security/defender/m365d-autoir) 機能をトリガーできるようになりました。

> [!IMPORTANT]
> Microsoft 365 Defenderとの統合の一環として、一部のオプションと詳細は Defender for Identity ポータルの場所から変更されています。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細を参照してください。

## <a name="review-security-alerts"></a>セキュリティ アラートを確認する

アラートには、 **アラート** ページ、 **インシデント** ページ、個々の **デバイス** のページ、 **高度なハンティング** ページなど、複数の場所からアクセスできます。 この例では、[ **アラート] ページ** を確認します。

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>で、[**インシデント&アラート**] に移動し、[**アラート]** に移動します。

:::image type="content" source="../../media/defender-identity/incidents-alerts.png" alt-text="[アラート] メニュー項目" lightbox="../../media/defender-identity/incidents-alerts.png":::

Defender for Identity からのアラートを表示するには、右上で **[フィルター**] を選択し、[**サービス ソース**] で **[Microsoft Defender for Identity**] を選択し、[**適用**] を選択します。

:::image type="content" source="../../media/defender-identity/filter-defender-for-identity.png" alt-text="Defender for Identity イベントのフィルター" lightbox="../../media/defender-identity/filter-defender-for-identity.png":::

アラートは、 **アラート名**、 **タグ**、 **重大度**、 **調査状態**、 **状態**、 **カテゴリ**、 **検出ソース**、 **影響を受けた資産**、 **最初のアクティビティ**、 **および最終アクティビティ** の情報と共に表示されます。

:::image type="content" source="../../media/defender-identity/filtered-alerts.png" alt-text="Defender for Identity イベント" lightbox="../../media/defender-identity/filtered-alerts.png":::

## <a name="manage-alerts"></a>アラートの管理

いずれかの **アラートの [アラート名** ] をクリックすると、アラートの詳細が表示されたページに移動します。 左側のウィンドウに、 **発生した** 内容の概要が表示されます。

:::image type="content" source="../../media/defender-identity/what-happened.png" alt-text="[What happened]\(発生した内容\) ウィンドウ" lightbox="../../media/defender-identity/what-happened.png":::

[ **処理** 内容] ボックスの上には、アラートの **アカウント**、 **宛先ホスト** 、 **およびソース ホスト** のボタンがあります。 その他のアラートについては、追加のホスト、アカウント、IP アドレス、ドメイン、およびセキュリティ グループの詳細に関するボタンが表示される場合があります。 いずれかのエンティティを選択して、関連するエンティティの詳細を取得します。

右側のウィンドウに、 **アラートの詳細** が表示されます。 詳細を確認し、いくつかのタスクを実行できます。

- **このアラートを分類** する - ここでは、このアラートを **True アラート** または **False アラート** として指定できます

    :::image type="content" source="../../media/defender-identity/classify-alert.png" alt-text="アラートを分類できるページ" lightbox="../../media/defender-identity/classify-alert.png":::

- **アラートの状態** - **[分類の設定]** では、アラートを **True** または **False** として分類できます。 **[割り当て対象**] で、アラートを自分に割り当てたり、割り当てを解除したりできます。

    :::image type="content" source="../../media/defender-identity/alert-state.png" alt-text="[アラート状態] ウィンドウ" lightbox="../../media/defender-identity/alert-state.png":::

- **アラートの詳細** - [ **アラートの詳細]** で、特定のアラートの詳細を確認し、アラートの種類に関するドキュメントへのリンクに従い、アラートが関連付けられているインシデントを確認し、このアラートの種類にリンクされている自動調査を確認し、影響を受けるデバイスとユーザーを確認できます。

   :::image type="content" source="../../media/defender-identity/alert-details.png" alt-text="[アラートの詳細] ページ" lightbox="../../media/defender-identity/alert-details.png":::

- **コメント&履歴** - ここでは、アラートにコメントを追加し、アラートに関連付けられているすべてのアクションの履歴を確認できます。

    :::image type="content" source="../../media/defender-identity/comments-history.png" alt-text="[コメント&履歴] ページ" lightbox="../../media/defender-identity/comments-history.png":::

- **アラートの管理** - [ **アラートの管理**] を選択した場合は、次を編集できるウィンドウに移動します。
  - **状態** - **[新規]**、[ **解決済み** ]、または **[進行中]** を選択できます。
  - **分類** - **[True アラート** ] または [ **False アラート]** を選択できます。
  - **コメント** - アラートに関するコメントを追加できます。

    **[アラートの管理**] の横にある 3 つのドットを選択した場合は、**脅威の専門家に問い合** わせてください。アラートをExcel ファイルに **エクスポート** するか、**別のインシデントにリンク** します。

    :::image type="content" source="../../media/defender-identity/manage-alert.png" alt-text="[アラートの管理] オプション" lightbox="../../media/defender-identity/manage-alert.png":::

    > [!NOTE]
    > Excel ファイルで、次の 2 つのリンクを使用できるようになりました。**Microsoft Defender for Identityで表示** し、**Microsoft 365 Defenderで表示** します。 各リンクは、関連するポータルにアクセスし、そこにアラートに関する情報を提供します。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender でアラートを調査する](../defender/investigate-alerts.md)
