---
title: 自動化された調査と応答 (AIR) の概要
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
ms.collection: M365-security-compliance
keywords: インシデント対応、調査、修復、脅威保護の自動化
ms.date: 09/29/2020
description: Microsoft Defender for Office 365 の自動調査および応答機能の概要を取得する
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: ce95b91aa67f76cf46ce3ed6285e24d3e9edd146
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308956"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の自動調査と応答 (AIR) の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


セキュリティの警告がトリガーされたときに、そのような警告を確認し、組織を保護するための手順を実行することは、セキュリティ運用チームにかかっています。 場合によっては、セキュリティ運用チームが、トリガーされた通知の量に圧倒されることがあります。 Microsoft Defender for Office 365 の自動調査と応答 (AIR) 機能を利用できます。 

AIR により、セキュリティ運用チームがより効率的かつ効果的に運用できるようになります。 空気機能には、今日の既知の脅威への対応として、自動化された調査プロセスが含まれます。 適切な修復処置で承認を受けることができ、セキュリティ運用チームが検出された脅威に対応できるようになります。 

この記事では、エアの概要について説明します。 AIR の使用を開始する準備ができたら、「 [脅威に自動的に調査して応答する](office-365-air.md)」を参照してください。

## <a name="at-a-high-level"></a>高レベル

アラートがトリガーされると、セキュリティのプレイブックが有効になります。 状況に応じて、自動化された [調査プロセス](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) を開始できます。 自動化された調査の最中および実行後に、 [修復アクション](air-remediation-actions.md) をお勧めします。 Office 365 では、Microsoft Defender で自動的にアクションは実行されません。 セキュリティ運用チームがレビューを行い、 [各修復アクションを承認または拒否](air-review-approve-pending-completed-actions.md)します。 調査に続くすべてのアクションが承認または拒否されると、調査は完了です。 これらのすべてのアクティビティは、Microsoft 365 セキュリティセンター () で追跡および表示 [https://security.microsoft.com](https://security.microsoft.com) できます。 (詳細については、「 [調査の詳細を表示](air-view-investigation-results.md#view-details-of-an-investigation)する」を参照してください)。

次のセクションでは、警告、セキュリティプレイブック、および動作の例の詳細について説明します。

## <a name="alerts"></a>アラート

[アラート](../../compliance/alert-policies.md#viewing-alerts)は、セキュリティ運用チームのインシデント対応ワークフローに対するトリガーを表します。 すべての脅威に対処しつつ、優先的に調査するアラートのセットを適切に特定することは簡単ではありません。 アラートへの調査を手動で実行する場合、セキュリティ運用チームは脅威からのリスクでエンティティ (コンテンツ、デバイス、ユーザーなど) をハントして関連付けなければなりません。 このようなタスクやワークフローは、非常に時間がかかる場合があり、複数のツールやシステムが関係しています。 AIR では、セキュリティイベントの調査と応答が自動化されています。キーセキュリティと脅威管理の警告を使用すると、セキュリティ応答プレイブックが自動的にトリガーされます。 

現時点では、次の種類のアラートポリシーから生成されたアラートは、エアに対して自動的に調査されます。  

- 悪意のある可能性がある URL のクリックが検出されました
- ユーザーがフィッシングとして報告した電子メール`*`
- 配信後に削除されたマルウェアを含む電子メールメッセージ`*`
- 配信後に削除されたフィッシング Url を含む電子メールメッセージ`*`
- 疑わしい電子メール送信パターンが検出された
- ユーザーが電子メールの送信を制限されている
- メールの手動調査をトリガーした管理者`*`

> [!NOTE]
> アスタリスク () のマークが付いたアラートに `*` は、電子メール通知がオフになっている Microsoft 365 セキュリティセンター内のそれぞれのアラートポリシーの *情報* 重要度が割り当てられます。 メール通知は、[アラート ポリシーの構成](../../compliance/alert-policies.md#alert-policy-settings)で有効にすることができます。 

アラートを表示するには、セキュリティ/コンプライアンス センターで、[**アラート**]  >  [**アラートの表示**] の順に選択します。 詳細情報を表示するアラートを選択し、通知を選択して詳細を表示します。次に、[**調査を表示**] リンクを使用して当該[調査](air-view-investigation-results.md#investigation-graph)に移動します。  

> [!NOTE]
> 情報通知は、既定では通知ビューに表示されません。 それらを表示するには、通知フィルターを変更して情報通知を含めます。

アラート管理システム、サービス管理システム、またはセキュリティ情報およびイベント管理 (SIEM) システムを使用してセキュリティ警告を管理する組織では、電子メール通知または [Office 365 Management ACTIVITY API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用して、そのシステムに通知を送信できます。 電子メールまたは API 経由の調査アラート通知には、Microsoft 365 セキュリティセンターで通知にアクセスするためのリンクが含まれており、割り当てられたセキュリティ管理者が調査にすばやく移動できます。

![調査にリンクされるアラート](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>セキュリティ プレイブック

セキュリティプレイブックは、Microsoft Defender for Office 365 と Microsoft の脅威保護の中核となるバックエンドポリシーです。 AIR で提供されるセキュリティプレイブックは、現実の一般的なセキュリティシナリオに基づいており、セキュリティ運用チームからのフィードバックに基づいて開発されています。 組織内で特定のアラートがトリガーされると、セキュリティによるプレイブックが自動的に開始されます。 アラートがトリガーされると、関連付けられたプレイブックは自動調査および応答システムによって実行されます。 この調査では、特定のアラートのプレイブックに基づいてアラートを分析し、関連するすべてのメタデータ (電子メールメッセージ、ユーザー、件名、送信者などを含む) を確認します。 調査の調査結果に基づいて、組織のセキュリティチームが脅威を制御し、軽減するために実行できる一連の操作を航空で推奨します。 

空気で得られるセキュリティプレイブックは、組織が現在直面している電子メールの最も頻繁な脅威に取り組むように設計されています。 これらは、Microsoft とお客様の資産を保護する人を含む、セキュリティ運用チームとインシデント対応チームからの入力に基づいています。

- ユーザーから報告されたフィッシング メッセージ
- URL-[verdict の変更] をクリックします。
- 配信後のマルウェア検出 (マルウェア ZAP)
- 配信後のフィッシング検出 ZAP (フィッシング ZAP)
- 危険として報告されたユーザー 
- 手動による電子メールの調査 (管理者によってエクスプローラーのマルウェア、フィッシング、またはすべての電子メールビューからトリガーされます)

プレイブックおよびプレイブックの更新は、完了するとリリースされます。 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap) にアクセスすると、準備中および近日公開予定のプレイブックを確認できます。

### <a name="playbooks-include-investigation-and-recommendations"></a>プレイブックには調査と推奨事項が含まれます

AIR では、各セキュリティ プレイブックに含まれるものは次のとおりです。 

- 電子メールのエンティティ (ファイル、Url、受信者、IP アドレスなど) のルートの調査
- 組織で受信した類似メールをさらに探す 
- 他の潜在的な脅威を特定し、相関関係を特定するための手順 
- 脅威に関する推奨修復処理

各高度な手順には、さまざまな手順が実行されており、脅威への深く、詳細で完全な応答が提供されます。

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
- チェックは、Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) および Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) に対して実行され、ユーザーによって報告された他の類似メッセージがあるかどうかを確認します。
- ユーザーに対する侵害があったかどうかがチェックされます。 このチェックは、Office 365、 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)、および [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)の間の信号を活用して、関連するすべてのユーザーアクティビティの異常を関連付けます。

捜索フェーズでは、リスクと脅威がさまざまな捜索手順に割り当てられます。 

修復は、プレイブックの最後のフェーズです。 このフェーズでは、調査および捜索フェーズに基づいて、修復手順が実行されます。 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>例: セキュリティ管理者が脅威エクスプローラーから調査を開始する

通知によってトリガーされる自動調査に加えて、組織のセキュリティ運用チームは [脅威エクスプローラー](threat-explorer.md)のビューから自動化された調査を開始することができます。  この調査では、Microsoft Defender インシデントおよび外部の SIEM ツールがこの調査がトリガーされたことを確認できるように、通知も作成されます。 

たとえば、エクスプローラーで **マルウェア** 表示を使用しているとします。 グラフの下にあるタブを使用して、[ **電子メール** ] タブを選択します。リストで1つ以上のアイテムを選択すると、[ **+ Actions** ] ボタンがアクティブになります。 

![選択されたメッセージを含むエクスプローラー](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

[ **Actions** ] メニューを使用して、 **トリガー調査**を選択できます。

![選択されたメッセージの [アクション] メニュー](../../media/explorer-malwareview-selectedemails-actions.jpg)

アラートによってトリガーされるプレイブックと同様、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を特定して相関関連を特定するための手順、これらの脅威を軽減するための推奨処置が含まれます。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>例: セキュリティ運用チームは、Office 365 Management Activity API を使用して、SIEM とそのエアを統合します。

Microsoft Defender for Office 365 の空気機能には、セキュリティ運用チームが脅威を監視および解決するために使用できる [詳細 & のレポート](air-view-investigation-results.md) が含まれています。 ただし、他のソリューションには空気の機能を統合することもできます。 例としては、セキュリティ情報およびイベント管理 (SIEM) システム、ケース管理システム、カスタムレポートソリューションなどがあります。 これらの種類の統合は、 [Office 365 Management ACTIVITY API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用して行うことができます。 

たとえば、組織では、既に AIR によって処理されたユーザーレポートフィッシング通知をセキュリティ運用チームが表示する方法を設定しています。 これらのソリューションは、関連するアラートを組織の SIEM サーバーおよびそのケース管理システムと統合します。 このソリューションは、セキュリティ運用チームが実際の脅威に時間と労力を集中できるように、誤検知の数を大幅に減らします。 このカスタムソリューションの詳細については、「 [Tech Community blog: Office 365 ATP および O365 管理 API を使用した SOC の有効性を向上させる](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)」を参照してください。

## <a name="next-steps"></a>次の手順

- [空気の使用を開始する](office-365-air.md)

- [Microsoft 365 ロードマップを参照して、計画およびリリースされたことを確認してください](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Microsoft 365 Defender の自動調査および応答機能の追加について説明します。](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
