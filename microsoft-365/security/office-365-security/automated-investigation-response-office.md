---
title: Microsoft Defender for Office 365での自動調査と対応のしくみ
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
description: Microsoft Defender for Office 365で自動調査と対応の機能がどのように機能するかを確認する
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78dc31c055f563f0f9f03bcf12642296459de491
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64974237"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365での自動調査と対応のしくみ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セキュリティ アラートがトリガーされると、セキュリティ運用チームがそれらのアラートを調べて、組織を保護するための手順を実行します。 セキュリティ運用チームは、トリガーされるアラートの量に圧倒される場合があります。 Microsoft Defender for Office 365の自動調査と対応 (AIR) 機能が役立ちます。

AIR を使用すると、セキュリティ運用チームがより効率的かつ効果的に運用できるようになります。 AIR 機能には、現在存在する既知の脅威に対応する自動調査プロセスが含まれます。 適切な修復アクションが承認を待ち、セキュリティ運用チームが検出された脅威に対応できるようにします。

この記事では、いくつかの例を通じて AIR のしくみについて説明します。 AIR の使用を開始する準備ができたら、「 [脅威を自動的に調査して対応する」を](office-365-air.md)参照してください。

- [例 1: ユーザーから報告されたフィッシング メッセージが調査プレイブックを起動する](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [例 2: セキュリティ管理者が脅威エクスプローラーから調査をトリガーする](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [例 3: セキュリティ運用チームが、Office 365 Management アクティビティ API を使用して AIR と SIEM を統合する](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>例: ユーザーから報告されたフィッシング メッセージによる調査プレイブックの起動

組織内のユーザーがフィッシング詐欺の試みと思われるメールを受信したとします。 このようなメッセージを報告するようにトレーニングされたユーザーは、 [レポート メッセージ アドイン](enable-the-report-message-add-in.md) または [レポート フィッシング アドインを](enable-the-report-phish-add-in.md) 使用して、分析のために Microsoft に送信します。 申請はシステムにも送信され、エクスプローラーの [ **申請]** ビュー (以前は **ユーザーから報告** されたビューと呼ばありました) に表示されます。 さらに、ユーザーから報告されたメッセージによって、システムベースの情報アラートがトリガーされ、調査プレイブックが自動的に起動されます。

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

- 同様の電子メール メッセージは、電子メール クラスターの検索によって識別されます。
- 信号は、[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)などの他のプラットフォームと共有されます。
- 不審なメール メッセージ内の悪意のあるリンクをユーザーがクリックしたかどうかが判断されます。
- Exchange Online Protection ([EOP](exchange-online-protection-overview.md) と ([Microsoft Defender for Office 365](defender-for-office-365.md)) 間でチェックが行われ、他の同様のメッセージがユーザーによって報告されているかどうかを確認します。
- ユーザーに対する侵害があったかどうかがチェックされます。 このチェックでは、Office 365、[Microsoft Defender for Cloud Apps](/cloud-app-security)、Azure Active Directory間のシグナル[が](/azure/active-directory)活用され、関連するユーザー アクティビティの異常が関連付けられます。

捜索フェーズでは、リスクと脅威がさまざまな捜索手順に割り当てられます。

修復は、プレイブックの最後のフェーズです。 このフェーズでは、調査および捜索フェーズに基づいて、修復手順が実行されます。

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>例: セキュリティ管理者が脅威エクスプローラーから調査を開始する

アラートによってトリガーされる自動調査に加えて、組織のセキュリティ運用チームは [、脅威エクスプローラー](threat-explorer.md)のビューから自動調査をトリガーできます。 この調査によってアラートも作成されるため、Microsoft 365 Defenderインシデントと外部 SIEM ツールは、この調査がトリガーされたことを確認できます。

たとえば、エクスプローラーで **[マルウェア** ] ビューを使用しているとします。 グラフの下にあるタブを使用して、[ **電子メール** ] タブを選択します。一覧で 1 つ以上の項目を選択すると、[ **+ アクション]** ボタンがアクティブ化されます。

:::image type="content" source="../../media/Explorer-Malware-Email-ActionsInvestigate.png" alt-text="選択したメッセージを含むエクスプローラー" lightbox="../../media/Explorer-Malware-Email-ActionsInvestigate.png":::

**[アクション]** メニューを使用して、[**調査のトリガー**] を選択できます。

:::image type="content" source="../../media/explorer-malwareview-selectedemails-actions.jpg" alt-text="選択したメッセージの [アクション] メニュー" lightbox="../../media/explorer-malwareview-selectedemails-actions.jpg":::

アラートによってトリガーされるプレイブックと同様、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を特定して相関関連を特定するための手順、これらの脅威を軽減するための推奨処置が含まれます。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>例: セキュリティ運用チームが、Office 365 Management アクティビティ API を使用して AIR と SIEM を統合する

Microsoft Defender for Office 365の AIR 機能には、セキュリティ運用チームが脅威の監視と対処に使用できる[レポート&詳細](air-view-investigation-results.md)が含まれます。 ただし、AIR 機能を他のソリューションと統合することもできます。 たとえば、セキュリティ情報とイベント管理 (SIEM) システム、ケース管理システム、カスタム レポート ソリューションなどがあります。 このような統合は、[Office 365 Management アクティビティ API](/office/office-365-management-api/office-365-management-activity-api-reference) を使用して行うことができます。

たとえば、最近、組織は、セキュリティ運用チームが AIR によって既に処理されたユーザー報告のフィッシング アラートを表示する方法を設定しました。 そのソリューションは、関連するアラートを組織の SIEM サーバーとそのケース管理システムと統合します。 このソリューションは、セキュリティ運用チームが実際の脅威に時間と労力を集中できるように、誤検知の数を大幅に減らします。 このカスタム ソリューションの詳細については、「[Tech Community ブログ: Microsoft Defender for Office 365と O365 Management API を使用して SOC の有効性を向上させる](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)」を参照してください。

## <a name="next-steps"></a>次の手順

- [AIR を使用した概要](office-365-air.md)
- [保留中または完了した修復アクションを表示する](air-review-approve-pending-completed-actions.md)
