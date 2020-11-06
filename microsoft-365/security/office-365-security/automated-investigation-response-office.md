---
title: Microsoft Defender for Office 365 での自動化された調査と応答 (AIR) の仕組み
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: インシデント対応、調査、修復、脅威保護の自動化
ms.date: 11/05/2020
description: Microsoft Defender for Office 365 での自動化された調査と応答機能の仕組みを参照してください。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 6923e283e4ec62de9e4a9c1d9196eb032724798d
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931960"
---
# <a name="how-automated-investigation-and-response-air-works-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 での自動化された調査と応答 (AIR) の仕組み

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

セキュリティの警告がトリガーされたときに、そのような警告を確認し、組織を保護するための手順を実行することは、セキュリティ運用チームにかかっています。 場合によっては、セキュリティ運用チームが、トリガーされた通知の量に圧倒されることがあります。 Microsoft Defender for Office 365 の自動調査と応答 (AIR) 機能を利用できます。

AIR により、セキュリティ運用チームがより効率的かつ効果的に運用できるようになります。 空気機能には、今日の既知の脅威への対応として、自動化された調査プロセスが含まれます。 適切な修復処置で承認を受けることができ、セキュリティ運用チームが検出された脅威に対応できるようになります。

この記事では、いくつかの例を使用した空気のしくみについて説明します。 AIR の使用を開始する準備ができたら、「 [脅威に自動的に調査して応答する](office-365-air.md)」を参照してください。

- [例 1: ユーザーから報告されたフィッシングメッセージが、調査のプレイブックを起動する](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [例 2: セキュリティ管理者が脅威エクスプローラーから調査をトリガーする](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [例 3: セキュリティ運用チームが Office 365 Management Activity API を使用して、SIEM に航空を統合する](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)


## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>例: ユーザーから報告されたフィッシング メッセージによる調査プレイブックの起動

組織内のユーザーが、フィッシング詐欺であると思われる電子メールを受信したとします。 このようなメッセージを報告するようにトレーニングされたユーザーは、 [レポートメッセージアドイン](enable-the-report-message-add-in.md) を使用して、分析のために Microsoft に送信します。 送信は、システムにも送信さ **れ、[送信] ビューの** エクスプローラーに表示されます (以前はユーザーによって **報告** されたビューと呼ばれています)。 さらに、ユーザーによって報告されたメッセージがシステムベースの情報通知をトリガーするようになります。これにより、調査のプレイブックが自動的に起動します。

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

- 同様の電子メールメッセージは、電子メールクラスター検索によって識別されます。
- このシグナルは、 [エンドポイントの Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)など、他のプラットフォームと共有されます。
- 不審なメール メッセージ内の悪意のあるリンクをユーザーがクリックしたかどうかが判断されます。
- チェックは、Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) および ([Microsoft Defender for Office 365](office-365-atp.md)) で行われ、ユーザーによって報告された他の類似メッセージがあるかどうかを確認します。
- ユーザーに対する侵害があったかどうかがチェックされます。 このチェックは、Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)、および [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)の間の信号を活用して、関連するすべてのユーザーアクティビティの異常を関連付けます。

捜索フェーズでは、リスクと脅威がさまざまな捜索手順に割り当てられます。 

修復は、プレイブックの最後のフェーズです。 このフェーズでは、調査および捜索フェーズに基づいて、修復手順が実行されます。 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>例: セキュリティ管理者が脅威エクスプローラーから調査を開始する

通知によってトリガーされる自動調査に加えて、組織のセキュリティ運用チームは [脅威エクスプローラー](threat-explorer.md)のビューから自動化された調査を開始することができます。  この調査では、Microsoft Defender インシデントおよび外部の SIEM ツールがこの調査がトリガーされたことを確認できるように、通知も作成されます。 

たとえば、エクスプローラーで **マルウェア** 表示を使用しているとします。 グラフの下にあるタブを使用して、[ **電子メール** ] タブを選択します。リストで1つ以上のアイテムを選択すると、[ **+ Actions** ] ボタンがアクティブになります。 

![選択されたメッセージを含むエクスプローラー](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

[ **Actions** ] メニューを使用して、 **トリガー調査** を選択できます。

![選択されたメッセージの [アクション] メニュー](../../media/explorer-malwareview-selectedemails-actions.jpg)

アラートによってトリガーされるプレイブックと同様、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を特定して相関関連を特定するための手順、これらの脅威を軽減するための推奨処置が含まれます。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>例: セキュリティ運用チームは、Office 365 Management Activity API を使用して、SIEM とそのエアを統合します。

Microsoft Defender for Office 365 の空気機能には、セキュリティ運用チームが脅威を監視および解決するために使用できる [詳細 & のレポート](air-view-investigation-results.md) が含まれています。 ただし、他のソリューションには空気の機能を統合することもできます。 例としては、セキュリティ情報およびイベント管理 (SIEM) システム、ケース管理システム、カスタムレポートソリューションなどがあります。 これらの種類の統合は、 [Office 365 Management ACTIVITY API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用して行うことができます。 

たとえば、組織では、既に AIR によって処理されたユーザーレポートフィッシング通知をセキュリティ運用チームが表示する方法を設定しています。 これらのソリューションは、関連するアラートを組織の SIEM サーバーおよびそのケース管理システムと統合します。 このソリューションは、セキュリティ運用チームが実際の脅威に時間と労力を集中できるように、誤検知の数を大幅に減らします。 このカスタムソリューションの詳細については、「Tech Community blog」を参照してください。 [Microsoft Defender For Office 365 および O365 管理 API を使用して SOC の効果を向上させる](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

## <a name="next-steps"></a>次のステップ

- [空気の使用を開始する](office-365-air.md)

- [Microsoft 365 ロードマップを参照して、計画およびリリースされたことを確認してください](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Microsoft 365 Defender の自動調査および応答機能について説明します。](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
