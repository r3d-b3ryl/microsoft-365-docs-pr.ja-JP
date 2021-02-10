---
title: Microsoft Defender for Office 365 での自動調査と対応のしくみ
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自動インシデント対応, 調査, 修復, 脅威の保護
ms.date: 01/29/2021
description: Microsoft Defender for Office 365 での自動調査と対応の機能について説明します。
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b187c5fee560e1ebf5463e889fff874aca05212d
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175825"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 での自動調査と対応のしくみ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

セキュリティの警告がトリガーされると、セキュリティ運用チームがそれらのアラートを確認し、組織を保護するための手順を実行する必要があります。 場合によっては、セキュリティ運用チームが、トリガーされるアラートの量に圧倒される可能性があります。 Microsoft Defender for Office 365 の自動調査および対応 (AIR) 機能が役立ちます。

AIR を使用すると、セキュリティ運用チームが効率的かつ効果的に運用できます。 AIR 機能には、現在存在する既知の脅威に対応する自動調査プロセスが含まれます。 適切な修復アクションは承認を待ち、セキュリティ運用チームが検出された脅威に対応できます。

この記事では、AIR がいくつかの例を通じてどのように機能するのかについて説明します。 AIR の使用を開始する準備ができたら、「脅威を自動的に調査して対応する」 [を参照してください](office-365-air.md)。

- [例 1: ユーザーから報告されたフィッシング メッセージが調査プレイブックを起動する](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [例 2: セキュリティ管理者が脅威エクスプローラーから調査を開始する](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [例 3: セキュリティ運用チームは、Office 365 マネージメント アクティビティ API を使用して AIR を SIEM と統合します。](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>例: ユーザーから報告されたフィッシング メッセージによる調査プレイブックの起動

組織内のユーザーがフィッシング詐欺と思うメールを受信したとします。 このようなメッセージを報告するトレーニングを受けたユーザーは、レポート [メッセージ](enable-the-report-message-add-in.md) アドインまたは [Report Phishing](enable-the-report-phish-add-in.md) アドインを使用して、分析のために Microsoft に送信します。 申請はシステムにも送信され、エクスプローラーの [ **提出** ] ビュー (以前はユーザーによって報告されたビューと呼ばばっていました) **に表示** されます。 さらに、ユーザーから報告されたメッセージによってシステムベースの情報アラートがトリガーされ、調査プレイブックが自動的に起動されます。

ルート調査フィーズでは、メールのさまざまな側面が評価されます。 次のような側面があります。

- 可能性のある脅威の種類の特定
- 誰が送信したか
- メールはどこから送信されたか (送信元のインフラストラクチャ)
- メールの他のインスタンスは、配信されたのか、それともブロックされたのか
- Microsoft のアナリストによる評価
- メールが既知のキャンペーンと関連するものかどうか
- その他

ルート調査が完了すると、元のメールとそれに関連付けられているエンティティに対する推奨処理の一覧がプレイブックにより提供されます。

次に、脅威の調査と捜索のための手順がいくつか実行されます。

- 同様の電子メール メッセージは、電子メール クラスター検索によって識別されます。
- 信号は、Microsoft Defender for Endpoint などの他 [のプラットフォームと共有されます](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。
- 不審なメール メッセージ内の悪意のあるリンクをユーザーがクリックしたかどうかが判断されます。
- チェックは、Exchange Online Protection ([EOP)](exchange-online-protection-overview.md)と ([Office 365](office-365-atp.md)の Microsoft Defender) を通して行われ、ユーザーによって報告された他の同様のメッセージが他にはないか確認します。
- ユーザーに対する侵害があったかどうかがチェックされます。 このチェックでは、Office 365、Microsoft Cloud [App Security、Azure](https://docs.microsoft.com/cloud-app-security) [Active Directory](https://docs.microsoft.com/azure/active-directory)のシグナルを活用して、関連するユーザー アクティビティの異常を関連付ける。

捜索フェーズでは、リスクと脅威がさまざまな捜索手順に割り当てられます。

修復は、プレイブックの最後のフェーズです。 このフェーズでは、調査および捜索フェーズに基づいて、修復手順が実行されます。

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>例: セキュリティ管理者が脅威エクスプローラーから調査を開始する

アラートによってトリガーされる自動調査に加えて、組織のセキュリティ運用チームは、脅威エクスプローラーのビューから自動調査 [をトリガーできます](threat-explorer.md)。  この調査ではアラートも作成され、Microsoft Defender インシデントと外部 SIEM ツールは、この調査がトリガーされたと確認できます。

たとえば、エクスプローラーの [マルウェア] ビュー **を** 使用するとします。 グラフの下のタブを使用して、[メール] タブ **を選択** します。リスト内の 1 つ以上のアイテムを選択すると、[+ **アクション] ボタン** がアクティブ化されます。

![選択されたメッセージを含むエクスプローラー](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

[操作] **メニューを使用** して、[調査のトリガー] **を選択できます**。

![選択したメッセージの [操作] メニュー](../../media/explorer-malwareview-selectedemails-actions.jpg)

アラートによってトリガーされるプレイブックと同様、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を特定して相関関連を特定するための手順、これらの脅威を軽減するための推奨処置が含まれます。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>例: セキュリティ運用チームは、Office 365 マネージメント アクティビティ API を使用して AIR を SIEM と統合します。

Office 365 向け Microsoft Defender の[](air-view-investigation-results.md)AIR 機能には、セキュリティ運用&チームが脅威の監視と対処に使用できる詳細なレポートが含まれます。 ただし、AIR 機能を他のソリューションと統合できます。 たとえば、セキュリティ情報とイベント管理 (SIEM) システム、ケース管理システム、カスタム レポート ソリューションなどです。 これらの種類の統合は、365 管理アクティビティ API Office [使用して実行できます](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。

たとえば最近、組織はセキュリティ運用チームが、AIR によって既に処理されているユーザーから報告されたフィッシングアラートを表示する方法をセットアップしました。 ソリューションは、関連するアラートを組織の SIEM サーバーとそのケース管理システムと統合します。 このソリューションは、セキュリティ運用チームが実際の脅威に時間と労力を集中できるよう、誤検知の数を大幅に減らします。 このカスタム ソリューションの詳細については、Tech Community ブログを参照してください [。microsoft Defender for Office 365 および O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)を使用して SOC の有効性を向上させる。

## <a name="next-steps"></a>次の手順

- [AIR の使用を開始する](office-365-air.md)
- [保留中または完了した修復アクションを表示する](air-review-approve-pending-completed-actions.md)
