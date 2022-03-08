---
title: Microsoft Defender for microsoft Defender for Office 365
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自動インシデント対応、調査、修復、脅威保護
ms.date: 01/29/2021
description: Microsoft Defender for microsoft Defender for Office 365 での自動調査と応答機能の動作を確認する
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ee046815f681b327fbcceaedf9033af9bfa5e109
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329517"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Microsoft Defender for microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セキュリティアラートがトリガーされると、セキュリティ運用チームがこれらのアラートを確認し、組織を保護するための手順を実行する必要があります。 場合によっては、セキュリティ運用チームがトリガーされるアラートの量に圧倒される場合があります。 Microsoft Defender for microsoft Defender の自動調査と応答 (AIR) 機能は、Office役立ちます。

AIR を使用すると、セキュリティ運用チームは、より効率的かつ効果的に運用できます。 AIR 機能には、現在存在する既知の脅威に対応する自動調査プロセスが含まれます。 適切な修復アクションは承認を待ち、セキュリティ運用チームが検出された脅威に対応できます。

この記事では、いくつかの例を通して AIR がどのように動作するのかについて説明します。 AIR の使用を開始する準備ができたら、「脅威を自動的に調査 [して対応する」を参照してください](office-365-air.md)。

- [例 1: ユーザーが報告したフィッシング メッセージが調査プレイブックを起動する](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [例 2: セキュリティ管理者が脅威エクスプローラーから調査をトリガーする](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [例 3: セキュリティ運用チームは、365 管理アクティビティ API を使用して AIR と SIEM を統合Office使用します。](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>例: ユーザーから報告されたフィッシング メッセージによる調査プレイブックの起動

組織内のユーザーがフィッシング詐欺の試みと思うメールを受信したとします。 このようなメッセージを報告するトレーニングを受けたユーザーは[](enable-the-report-message-add-in.md)、レポート メッセージ アドインまたはレポート フィッシング [](enable-the-report-phish-add-in.md) アドインを使用して、分析のために Microsoft に送信します。 申請はシステムにも送信され、[申請] ビュー (以前はユーザーレポート  ビューと呼ばば) の **エクスプローラーに表示** されます。 さらに、ユーザーが報告したメッセージによってシステムベースの情報アラートがトリガーされ、調査プレイブックが自動的に起動されます。

ルート調査フィーズでは、メールのさまざまな側面が評価されます。 これらの側面は次のとおりです。

- 可能性のある脅威の種類の特定
- 誰が送信したか
- メールはどこから送信されたか (送信元のインフラストラクチャ)
- メールの他のインスタンスは、配信されたのか、それともブロックされたのか
- Microsoft のアナリストによる評価
- メールが既知のキャンペーンと関連するものかどうか
- その他

ルート調査が完了すると、元のメールとそれに関連付けられているエンティティに対する推奨処理の一覧がプレイブックにより提供されます。

次に、脅威の調査と捜索のための手順がいくつか実行されます。

- 同様の電子メール メッセージは、電子メール クラスター検索を介して識別されます。
- 信号は、Microsoft [Defender for Endpoint などの他のプラットフォームと共有されます](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。
- 不審なメール メッセージ内の悪意のあるリンクをユーザーがクリックしたかどうかが判断されます。
- チェックは、Exchange Online Protection ([EOP](exchange-online-protection-overview.md) および ([Microsoft Defender for Office 365](defender-for-office-365.md) ) で行われ、ユーザーが報告した他の同様のメッセージが表示される場合があります。
- ユーザーに対する侵害があったかどうかがチェックされます。 このチェックでは、Office 365、 [Microsoft Defender for Cloud Apps](/cloud-app-security)、 [Azure Active Directory](/azure/active-directory) の信号を活用して、関連するユーザー アクティビティの異常を関連付ける。

捜索フェーズでは、リスクと脅威がさまざまな捜索手順に割り当てられます。

修復は、プレイブックの最後のフェーズです。 このフェーズでは、調査および捜索フェーズに基づいて、修復手順が実行されます。

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>例: セキュリティ管理者が脅威エクスプローラーから調査を開始する

アラートによってトリガーされる自動調査に加えて、組織のセキュリティ運用チームは、脅威エクスプローラーのビューから自動調査 [をトリガーできます](threat-explorer.md)。  この調査ではアラートも作成され、Microsoft 365 Defender インシデントと外部 SIEM ツールは、この調査がトリガーされたと確認できます。

たとえば、エクスプローラーでマルウェア ビューを **使用すると** します。 グラフの下のタブを使用して、[メール] タブ **を選択** します。リストで 1 つ以上のアイテムを選択すると、[ **+ アクション] ボタンが** アクティブ化されます。

![選択したメッセージを含むエクスプローラー。](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

[アクション] **メニューを** 使用して、[調査のトリガー **] を選択できます**。

![選択したメッセージの [アクション] メニュー。](../../media/explorer-malwareview-selectedemails-actions.jpg)

アラートによってトリガーされるプレイブックと同様、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を特定して相関関連を特定するための手順、これらの脅威を軽減するための推奨処置が含まれます。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>例: セキュリティ運用チームは、365 管理アクティビティ API を使用して AIR と SIEM を統合Office使用します。

Microsoft Defender for Office 365 の AIR 機能には、セキュリティ&チームが[](air-view-investigation-results.md)脅威の監視と対処に使用できる詳細なレポートが含まれます。 ただし、AIR 機能を他のソリューションと統合できます。 たとえば、セキュリティ情報とイベント管理 (SIEM) システム、ケース管理システム、またはカスタム レポート ソリューションがあります。 これらの種類の統合は、 [365 管理アクティビティ API Office使用して実行できます](/office/office-365-management-api/office-365-management-activity-api-reference)。

たとえば、最近、組織はセキュリティ運用チームが AIR によって既に処理されたユーザーが報告したフィッシングアラートを表示する方法をセットアップしました。 ソリューションは、関連するアラートを組織の SIEM サーバーとそのケース管理システムと統合します。 このソリューションは、セキュリティ運用チームが実際の脅威に時間と労力を集中できるよう、誤検知の数を大幅に削減します。 このカスタム ソリューションの詳細については、「Tech [Community blog: improve the EFFECTIVENESS of your SOC with Microsoft Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)」を参照してください。

## <a name="next-steps"></a>次の手順

- [AIR の使用を開始する](office-365-air.md)
- [保留中または完了した修復アクションの表示](air-review-approve-pending-completed-actions.md)
