---
title: Microsoft Defender for Identity security alerts in <DICT__Microsoft⚐365⚐Defender>Microsoft 365 Defender</DICT__Microsoft⚐365⚐Defender>
description: Microsoft Defender for Identity が発行したセキュリティ アラートを管理および確認する方法については、Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 98df694002d31e330fff1b5d53618044bc6c5dae
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58566666"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Defender for Identity security alerts in Microsoft 365 Defender

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、Microsoft Defender for [Identity](/defender-for-identity)のセキュリティ アラートを使用する方法の基本について説明[Microsoft 365 Defender。](/microsoft-365/security/defender/overview-security-center)

Defender for Identity アラートは、専用の IDENTITY アラート[ページ](https://security.microsoft.com)Microsoft 365 Defenderにネイティブに統合されます。 これは、Microsoft Defender for [Identity](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)エクスペリエンス全体を新しいユーザーエクスペリエンスに導入する最初のステップMicrosoft 365 Defender。

新しい Identity アラート ページでは、Microsoft Defender for Identity のお客様にクロスドメインシグナルエンリッチメントと新しい自動 ID 応答機能を提供します。 これにより、セキュリティを確保し、セキュリティ操作の効率を向上させることができます。

Microsoft 365 Defender を使用してアラートを調査する利点の[1](/microsoft-365/security/defender/microsoft-365-defender)つは、Microsoft Defender for Identity アラートがスイート内の他の各製品から得られた情報とさらに関連付けられているという利点があります。 これらの拡張アラートは、Microsoft Defender for Microsoft 365 Defenderおよび Microsoft Defender [for](/microsoft-365/security/office-365-security) Endpoint から発信される他Office 365のアラート形式と[一致しています](/microsoft-365/security/defender-endpoint)。 新しいページでは、ID に関連付けられたアラートを調査するために別の製品ポータルに移動する必要が実質的になくされます。

Defender for Identity から発生したアラートは、Microsoft 365 Defender の自動調査と応答[(AIR)](/microsoft-365/security/defender/m365d-autoir)機能をトリガーできます。アラートの自動修復や、疑わしいアクティビティに寄与する可能性があるツールとプロセスの軽減を含む。

> [!IMPORTANT]
> Id ポータルの Defender の場所Microsoft 365 Defender一部のオプションと詳細が変更されました。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細をお読みください。

## <a name="review-security-alerts"></a>セキュリティアラートの確認

アラートには、[アラート] ページ、インシデント ページ、個々のデバイスのページ、高度な検索ページなど、複数の **場所からアクセス** できます。 この例では、[アラート] ページを **確認します**。

[[Microsoft 365 Defender]](https://security.microsoft.com/)で、[インシデント] **&に移動し**、[アラート] に **移動します**。

![[インシデントと通知] の順に移動し、[アラート] をクリックします。](../../media/defender-identity/incidents-alerts.png)

Defender for Identity からのアラートを表示するには、上部の[フィルター]を選択し、[サービス ソース] で **[Microsoft Defender for Identity]** を選択し、[適用] を **選択します**。

![Defender for Identity イベントのフィルター。](../../media/defender-identity/filter-defender-for-identity.png)

アラートは、アラート名、タグ、**重大度**、**調査** 状態、**状態**、**カテゴリ**、検出ソース、影響を受けた資産、**最初** のアクティビティ、および最後のアクティビティの情報と一緒に **表示されます**。 

![Defender for Identity イベント。](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a>アラートの管理

アラートの **1 つの [アラート名** ] をクリックすると、アラートの詳細が表示されたページに移動します。 左側のウィンドウに、[発生した操作] の概要 **が表示されます**。

![アラートで何が起こったか。](../../media/defender-identity/what-happened.png)

[何が **起こったか]** ボックスの上には、アラートの **アカウント、宛先****ホスト**、および **送信元ホストの** ボタンがあります。 その他のアラートについては、追加のホスト、アカウント、IP アドレス、ドメイン、セキュリティ グループの詳細についてボタンが表示される場合があります。 関係するエンティティの詳細を取得するには、それらを選択します。

右側のウィンドウに、アラートの詳細が **表示されます**。 ここでは、詳細を確認し、いくつかのタスクを実行できます。

- **このアラートを分類** する - ここでは、このアラートを True アラートまたは **False アラート** として **指定できます。**

    ![アラートを分類します。](../../media/defender-identity/classify-alert.png)

- **アラートの状態** - [ **分類の設定]** で、アラートを True または **False に** 分類 **できます**。 [ **割り当て** 済み] で、アラートを自分に割り当てたり、割り当てを解除することができます。

    ![アラートの状態。](../../media/defender-identity/alert-state.png)

- **アラートの** 詳細 - **[アラート** の詳細] で、特定のアラートに関する詳細情報を確認し、アラートの種類に関するドキュメントへのリンクを参照し、アラートが関連付けられているインシデントを確認し、このアラートの種類にリンクされている自動調査を確認し、影響を受けたデバイスとユーザーを確認できます。

    ![アラートの詳細。](../../media/defender-identity/alert-details.png)

- **コメント&履歴** - アラートにコメントを追加し、アラートに関連付けられているすべてのアクションの履歴を確認できます。

    ![コメントと履歴。](../../media/defender-identity/comments-history.png)

- **警告の** 管理 - [警告の **管理] を** 選択すると、次のウィンドウを編集できます。
  - **[状態**] - [新規 **]、[****解決済み]、** または [進行中]**を選択できます**。
  - **分類** - [True アラート] **または [False アラート** ] **を選択できます**。
  - **コメント** - アラートに関するコメントを追加できます。

    [警告の管理] の横にある 3 つのドットを選択すると、脅威の専門家に相談したり、アラートを Excel ファイルにエクスポートしたり、別のインシデントに **リンク** することができます。 

    ![アラートを管理します。](../../media/defender-identity/manage-alert.png)

    > [!NOTE]
    > このファイルExcel、使用可能なリンクが 2 つ用意されています **。[Id** の Microsoft Defender での表示] と [Id の表示] の 2 つの **リンク** Microsoft 365 Defender。 各リンクを使用すると、関連するポータルにアクセスし、そこにアラートに関する情報を提供します。

## <a name="see-also"></a>関連項目

- [[アラートの調査] Microsoft 365 Defender](../defender/investigate-alerts.md)
