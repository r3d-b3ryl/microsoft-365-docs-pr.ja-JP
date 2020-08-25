---
title: 自動調査および対応 (AIR) の概要
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
ms.date: 08/21/2020
description: 365 Advanced Threat Protection プラン 2 の自動調査 Officeと対応機能の概要を説明します。
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: 27a2330d5f1ff339aabf6a0fccb94a15dec30852
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860723"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a>Microsoft 365 での自動調査および対応 (AIR) の概要

セキュリティの警告がトリガーされた場合、セキュリティ運用チームはこれらのアラートを調査し、組織を保護するための手順を実行する必要があります。 セキュリティ運用チームは、トリガーされたアラートの量に過大感していると感じえることがあります。 Office 365 Advanced Threat Protection (Office 365 ATP) の自動調査および対応 (AIR) 機能が役立ちます。 

セキュリティ運用チームは AIR を使用して、いつも効率よく、かつ効果的に運用することができます。 AIR 機能には、現在存在している既知の脅威に対する自動調査プロセスが含まれています。 適切な修復アクションは承認を待ち、セキュリティ運用チームが検出された脅威に対応することができます。 

この記事では、AIR の概要について説明します。 AIR の使用を開始する準備ができたら、「自動的 [に脅威を調査し対応する」を参照してください](office-365-air.md)。

## <a name="at-a-high-level"></a>その上位レベル

アラートがトリガーされると、セキュリティ プレイブックが有効になります。 状況に応じて、 [自動調査プロセスが](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) 開始できます。 自動調査の実行中と、修復アクション [をお](air-remediation-actions.md) 勧めします。 Advanced Threat Protection では、自動的にOfficeは行いなけれていけれない。 セキュリティ運用チームが確認し、その後 [、修復アクションをそれぞれ承認または拒否します](air-review-approve-pending-completed-actions.md)。 調査に取り組みるすべての操作が承認または拒否されると、調査は完了します。 これらのアクティビティはすべて、セキュリティ センター コンプライアンス センターで追跡 &表示できます (調査[の詳細を表示)。](air-view-investigation-results.md#view-details-of-an-investigation)

以下のセクションでは、アラート、セキュリティ プレイブック、動作中の AIR の例について詳しく説明します。

## <a name="alerts"></a>アラート

[アラート](../../compliance/alert-policies.md#viewing-alerts)は、セキュリティ運用チームのインシデント対応ワークフローに対するトリガーを表します。 すべての脅威に対処しつつ、優先的に調査するアラートのセットを適切に特定することは簡単ではありません。 アラートの調査を手動で実行する場合、セキュリティ運用チームは、脅威の危険に応じてエンティティ (コンテンツ、デバイス、ユーザーなど) を検索し、対応付けする必要があります。 このようなタスクやワークフローは非常に時間がかかり、複数のツールとシステムを必要とする可能性があります。 AIR を使用すると、セキュリティ イベントの調査と対応は、主要なセキュリティおよび脅威の管理の警告を用意して、セキュリティ対応プレイブックを自動的にトリガーすると自動的に実行されます。 

現在、AIR では、次の種類のアラート ポリシーから生成されたアラートは自動的に調査されます。  

- 悪意のある可能性がある URL のクリックが検出されました
- ユーザーによりフィッシングとして報告された電子メール`*`
- マルウェアを含む電子メール メッセージが配信後に削除されました`*`
- フィッシング URL が含まれるメール メッセージが配信後に削除されました`*`
- 不審なメール送信パターンが検出されました`#`
- メール送信が制限されているユーザー`#`

> [!NOTE]
> アスタリスク ( ) が付けられているアラートには、セキュリティ & コンプライアンス センター内の各アラート ポリシーに情報重大 `*` 度が割り当てられ、電子メール通知は無効になります。 *Informational* メール通知は、[アラート ポリシーの構成](../../compliance/alert-policies.md#alert-policy-settings)で有効にすることができます。 ハッシュ ( ) が付けられたアラート `#` は、パブリック プレビュー プレイブックに関連付けられている、一般的に利用可能なアラートです。

アラートを表示するには、セキュリティ/コンプライアンス センターで、[**アラート**]  >  [**アラートの表示**] の順に選択します。 詳細情報を表示するアラートを選択し、通知を選択して詳細を表示します。次に、[**調査を表示**] リンクを使用して当該[調査](air-view-investigation-results.md#investigation-graph)に移動します。  

> [!NOTE]
> 既定では、情報通知はアラート ビューでは表示されません。 表示するには、アラート フィルターを変更して情報アラートを含める必要があります。

組織がアラート管理システム、サービス管理システム、またはセキュリティ情報イベント管理 (SIEM) システムを通じてセキュリティの警告を管理している場合、電子メール通知または [Office 365 管理アクティビティ API を介して、そのシステムへのアラートを送信できます](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 メールまたは API 経由の調査アラート通知には、セキュリティ/コンプライアンス センターでアラートにアクセスするためのリンクが含まれているので、割り当てられているセキュリティ管理者は簡単に調査に移動できます。

![調査にリンクされるアラート](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>セキュリティ プレイブック

セキュリティ プレイブックは、Advanced Threat Protection と Microsoft Threat Protection の自動化の中で行Officeされるバックエンド ポリシーです。 AIR で提供されるセキュリティ プレイブックは、一般的な実際のセキュリティ シナリオに基づいており、セキュリティ運用チームからのフィードバックに基づいて開発されます。 組織内で特定のアラートがトリガーされると、セキュリティ プレイブックが自動的に起動します。 アラートがトリガーされると、関連付けられているプレイブックは AIR (自動調査および応答) システムによって実行されます。 調査ステップは、アラートのプレイブックに基づくアラートを分析し、関連付けられているすべてのメタデータ (メール メッセージ、ユーザー、件名、送信者など) を対象とします。 調査プレイブックの調査結果に基づいて、AIR では脅威を制御および軽減するために組織のセキュリティ チームが実行できる一連の処理をお勧めします。 

AIR に付くセキュリティ プレイブックは、組織が現在メールで現在直近する最も一般的な脅威に対処するための設計です。 これらは、Microsoft およびお客様のアセットの保護に関する人など、セキュリティ運用チームおよびインシデント対応チームからの意見に基づいています。

### <a name="security-playbooks-are-rolling-out-in-phases"></a>セキュリティ プレイブックは段階的に展開されています

セキュリティ プレイブックは AIR の一環として段階的に展開されています。 フェーズ 1 は現在一般公開されており、セキュリティ管理者が確認して承認できる処理に関する推奨事項を提供する、いくつかのプレイブックが含まれています。

- ユーザーから報告されたフィッシング メッセージ
- URL-click verdict change
- 配信後のマルウェア検出 (マルウェア ZAP)
- 配信後のフィッシング検出 ZAP (フィッシング ZAP)

フェーズ 1 では、管理者がメール調査をトリガーした (脅威エクスプローラーを使用した) サポートも [含まれています](threat-explorer.md)。

フェーズ 2 は、パブリック プレビューの以下のプレイブックで進 **め、アクション**に関する推奨事項の提供、問題の調査に対するセキュリティ管理者の対応を提供しています。

- ユーザーから報告された侵害の発生 (パブリック プレビュー)

その他のプレイブックは、完成すると解放されます。 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap) にアクセスすると、準備中および近日公開予定のプレイブックを確認できます。

### <a name="playbooks-include-investigation-and-recommendations"></a>プレイブックには調査と推奨事項が含まれます

AIR では、各セキュリティ プレイブックに含まれるものは次のとおりです。 

- メールのエンティティ (ファイル、URL、受信者、IP アドレスなど) のルート調査
- 組織が受信した類似メールの詳細な検索 
- 他の潜在的な脅威を特定し、相関関係を特定するための手順 
- 脅威に関する推奨修復処理

大まかに実行する各手順には、脅威に対する詳細かつ詳細な対応を提供するために実行されるいくつかのサブステップが含まれます。

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>例: ユーザーから報告されたフィッシング メッセージによる調査プレイブックの起動

組織内のユーザーがメールを受信して、そのユーザーがフィッシング行なのとみなしたとします。 そのようなメッセージを報告するためにトレーンで送信されたユーザーは、 [分析のため](enable-the-report-message-add-in.md) 、メッセージ報告アドインを使用して Microsoft に送信します。 申請はシステムにも送信され、送信ビュー (ユーザーから報告された**Submissions**ビューと呼ばれる)**のエクスプローラーに表示**されます。 また、ユーザーから報告されたメッセージによってシステム ベースの情報アラートがトリガーされ、調査プレイブックが自動的に起動します。

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

- 同様のメール メッセージは、メール クラスター検索によって識別されます。
- シグナルが [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) などの他のプラットフォームと共有されます。
- 不審なメール メッセージ内の悪意のあるリンクをユーザーがクリックしたかどうかが判断されます。
- ユーザーから報告された類似したメッセージが他に存在しているかどうかを確認するために、Exchange Online Protection[(EOP)](exchange-online-protection-overview.md)と Office 365 Advanced Threat Protection[(ATP)](office-365-atp.md)全体がチェックされます。
- ユーザーに対する侵害があったかどうかがチェックされます。 このチェックでは、Office 365、Microsoft [Cloud App Security、](https://docs.microsoft.com/cloud-app-security)[および Azure Active Directory](https://docs.microsoft.com/azure/active-directory)のシグナルを利用して、関連するすべてのユーザー アクティビティの異常を関連付けています。

捜索フェーズでは、リスクと脅威がさまざまな捜索手順に割り当てられます。 

修復は、プレイブックの最後のフェーズです。 このフェーズでは、調査および捜索フェーズに基づいて、修復手順が実行されます。 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>例: セキュリティ管理者が脅威エクスプローラーから調査を開始する

組織のセキュリティ運用チームは、警告によってトリガーされる自動調査の他に、脅威エクスプローラーのビューから自動調査を [トリガーすることもできます](threat-explorer.md)。

たとえば、脅威エクスプローラーの [マルウェア] ビュー **を使用** しているとします。 グラフの下のタブを使用して、[メール] タブ **を選択** します。一覧で 1 つまたは複数の項目を選択すると **、[+Actions] ボタンが** アクティブになります。 

![選択したメッセージを含むエクスプローラー](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

[アクション **] メニュー** を使用して、[調査の **開始] を選択できます**。

![選択したメッセージのアクション メニュー](../../media/explorer-malwareview-selectedemails-actions.jpg)

アラートによってトリガーされるプレイブックと同様、エクスプローラーのビューからトリガーされる自動調査には、ルート調査、脅威を特定して相関関連を特定するための手順、これらの脅威を軽減するための推奨処置が含まれます。

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>例: セキュリティ運用チームが、Office 365 管理アクティビティ API を使用して、AIR を SIEM と統合する

Office 365 ATP の AIR 機能には、 [セキュリティ運用チームが脅威を監視 &および対応するために使用できる](air-view-investigation-results.md) 詳細情報のレポートが含まれています。 AIR の機能を他のソリューションに統合することもできます。 セキュリティ情報とイベント管理 (SIEM) システム、ケース管理システム、カスタム レポート ソリューションなどが含まれます。 この種の統合は [、365 管理アクティビティ API Office使用して行えます](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 

たとえば、最近、組織は、セキュリティ運用チームが、AIR によって既に処理された、ユーザーから報告されたフィッシング アラートを表示する方法を設定しました。 ソリューションによって、関連する警告が組織の SIEM サーバーとそのケース管理システムに統合されます。 ソリューションでは、誤検知の数が大きく削減され、セキュリティ運用チームのセキュリティ運用チームは実際の脅威に対する時間と作業を集中できます。 このカスタム ソリューションの詳細については [、Tech Community ブログ「Office 365 ATP および O365 管理 API を使用して SOC の効果を向上させる」ブログを参照してください](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

## <a name="next-step"></a>次のステップ

- [AIR の使用を開始する](office-365-air.md)

## <a name="see-also"></a>関連項目

- [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Microsoft Threat Protection での自動調査および対応機能](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide)