---
title: Microsoft 365 セキュリティ センターの概要
description: Microsoft 365 セキュリティ センターの利点。Microsoft Defender for Office 365 (MDO) と Microsoft Defender for Endpoint (MDE) を、Microsoft Defender for Identity (MDI) および Microsoft Cloud App Security (MCAS) と組み合わせたもの。 この記事では、管理者向け Microsoft 365 セキュリティ センターの進歩の概要を説明します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, 監視, レポート, ID, データ, デバイス, アプリ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 89e72d703bd70647d6c2b00732315b8e5f015cc7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167203"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>統合 Microsoft 365 セキュリティ センターの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender for Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> Microsoft 365 Defender を体験したい場合 ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。

強化された **Microsoft 365** セキュリティ センター ( ) は、中央ポータルの電子メール、 [https://security.microsoft.com](https://security.microsoft.com) *コラボレーション**、ID、* デバイスの脅威に対する保護、検出、調査、応答を組み合わせたものになります。 

Microsoft 365 セキュリティ センターは、Microsoft Defender セキュリティ センターや Office 365 セキュリティ/コンプライアンス センターなど、既存の Microsoft セキュリティ ポータル&しています。 セキュリティ センターでは、情報への迅速なアクセス、より簡単なレイアウト、および関連する情報の組み合わせて使いやすくなっています。 このセンターには以下が含まれます。

- **[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender for Office 365 は、組織が電子メールを保護し、365 リソースを保護するための一連の予防、検出、調査、捜Officeを支援します。
- **[Microsoft Defender for Endpoint は](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** 、組織内のデバイスに対して予防的な保護、侵害後の検出、自動調査、対応を提供します。
- **[Microsoft 365 Defender は、Microsoft 365](microsoft-threat-protection.md)** セキュリティ ポートフォリオを活用してドメイン間の脅威データを自動的に分析し、1 つのダッシュボードで攻撃の画像を作成する Microsoft の *拡張* 検出と対応 (XDR) ソリューションの一部です。

Office 365 Security & コンプライアンス センターまたは Microsoft Defender セキュリティ センターからの変更点に関する情報が必要な場合は、次を参照してください。

- [Microsoft 365 Office 365 用 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft 365 セキュリティ センターのエンドポイント用 Defender](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>期待される問題

Office 365 セキュリティ/コンプライアンス センター (protection.office.com) と Microsoft Defender セキュリティ センター (securitycenter.microsoft.com) で使用しているすべてのセキュリティ コンテンツは *、Microsoft 365* セキュリティ センターで見つかる可能性があります。

Microsoft 365 セキュリティ センターは、セキュリティ チームがさまざまなワークロードからのシグナルを単一の統一されたエクスペリエンスに収め、攻撃の調査と対応を行うのに役立ちます。

- インシデント&アラート
- ハンティング
- アクション センター
- 脅威分析

Microsoft 365 セキュリティ センターでは、microsoft Defender for Office 365 と Microsoft Defender for Endpoint が統合され、統一性、明瞭さ、共通の目標が強調されています。 マージは、以下の優先順位に基づいており、各セキュリティ スイートが組み合わせに持ち込んだ機能を犠牲にせずに行いました。

- 共通の構成要素
- 一般的な用語
- 共通エンティティ
- 他のワークロードとの機能パリティ

## <a name="unified-investigations"></a>統合された調査

セキュリティ センターの合理化によって、Microsoft 365 組織全体のインシデントを調査する 1 つのウィンドウが作成されます。 主な例 **は、Microsoft** 365 セキュリティ センターのクイック起動の Incidents ノードです。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO の [Incidents] ページ。":::

たとえば、重大度が高いインシデント名をダブルクリックすると、収束センターの利点を示すページが表示されます。

![複数のエンドポイントでの特権エスカレーションを伴う多段階インシデント。影響を受けた 16 台のデバイスと 9 人の影響を受けたユーザーが表示されます。](../../media/converged-incident-info-3.png)

> [!TIP]
> [コンバージド **ユーザー]** タブは、問い合わせを始めるのに便利な場所です。 この単一ページでは、統合されたワークロード (Microsoft Defender for Endpoint、Microsoft Defender for Identity、MCAS を活用している場合)、およびオンプレミスの Active Directory、Azure Active Directory、同期済み、ローカル、およびサード パーティのユーザーなど、さまざまなソースからの情報が表示されます。 新しいユーザー [エクスペリエンスについて詳しくは、以下を参照してください](investigate-users.md)。

インシデント情報には、影響を受けるメールボックスの他に、ユーザー/ID 固有のデバイスと危険なデバイスが表示されます。 また、調査情報と **収集された** エビデンスも関連 **付けされます**。 これにより、管理者とセキュリティ運用チームは、リスクの高い 1 つの警告から影響を受けるユーザーやメールボックスに簡単にピボットできます。 このページの上部にある [ **インシデント** ] タブを見て、この 1 つの場所から他の主要なセキュリティ ピボットを使用できます。

> [!IMPORTANT]
> 特定のインシデントの任意のページの上部に、[概要]、[アラート]、[デバイス **]、[** ユーザー  **]、[** メールボックス **]、[** 調査]、および [エビデンス] タブが **表示** されます。

[調査 **] を** 選択すると、分析のグラフィックが表示されたページが開き、修復の状態 (承認待 **ちなど)** が一覧表示されます。 環境内の特定のインシデントを選択し、これらのタブにドリルダウンして、さまざまな種類の脅威のプロファイルを作成する方法について説明します。 慣れ親しみは、後で調査を進める上で有益です。

## <a name="improved-processes"></a>改善されたプロセス

共通のコントロールとコンテンツは、同じ場所に表示されるか、データの 1 つのフィードに要約され、見つけやすくなります。 たとえば、統合設定です。

### <a name="unified-settings"></a>統合設定

![Clicked 'Roles' and opened the Settings page, which includes General settings, Permissions, APIs and Rules. [アクセス許可] を開き、[ロール] を開きます。 すべてのロールを表示](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>ロール&アクセス許可

![グループ&デバイス グループのエンドポイントの役割を&を示す [アクセス許可] ページ](../../media/converged-roles-5.png)

 Microsoft 365 セキュリティ センターへのアクセスは、Azure Active Directory グローバル ロールまたはカスタム ロールを使用して構成されます。 エンドポイント用 Defender については、「Microsoft Defender セキュリティ センター [へのユーザー アクセスの割り当て」をご覧ください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access)。 Defender for Office 365 については [、Microsoft 365](../office-365-security/permissions-microsoft-365-compliance-security.md)コンプライアンス センターと Microsoft 365 セキュリティ センターの「アクセス許可」を参照してください。

- [Microsoft 365 Defender へのアクセスを管理する方法の詳細](mtp-permissions.md)
- Microsoft 365 セキュリティ センター [でカスタム ロール](custom-roles.md) を作成する方法の詳細

### <a name="integrated-reports"></a>統合レポート

レポートは、Microsoft 365 セキュリティ センターでも統合されています。 管理者は、一般的なセキュリティ レポートから始め、エンドポイント、電子メール、コラボレーションに関する特定のレポート&できます。 ここに示すリンクは、ワークロード構成に基づいて動的に生成されます。

### <a name="quickly-view-your-microsoft-365-environment"></a>Microsoft 365 環境をすばやく表示する

ホーム **ページには** 、セキュリティ チームが必要とする一般的なカードの多くが表示されます。 カードとデータの構成は、ユーザー ロールによって異なります。 Microsoft 365 セキュリティ センターでは役割ベースのアクセス制御が使用されるので、さまざまな役割で、毎日のジョブにとってより意味のあるカードが表示されます。  

この一目でわかる情報は、組織内の最新のアクティビティを把握するのに役立ちます。 Microsoft 365 セキュリティ センターは、さまざまなソースからのシグナルをまとめ、Microsoft 365 環境の全体像を表示します。

カードは、次のカテゴリに分類されます。

- **ID -** 組織内の ID を監視し、疑わしい動作や危険な動作を追跡します。 [ID 保護について詳しくは、次のリンクを参照してください](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。
- **データ** - 許可されていないデータの漏えいにつながる可能性があるユーザーアクティビティを追跡するのに役立ちます。
- **デバイス** - デバイス上のアラート、侵害アクティビティ、その他の脅威に関する最新の情報を取得します。
- **アプリ** - クラウド アプリが組織でどのように使用されているのかについての洞察を得る。 [Cloud App Security で検出されたアプリについて詳しくは、次のリンクを参照してください](https://docs.microsoft.com/cloud-app-security/discovered-apps)。

## <a name="threat-analytics-with-better-data-coverage"></a>データ範囲が向上した脅威分析
次の Microsoft 365 Defender 脅威分析統合エクスペリエンスを使用して、新たな脅威を追跡して対応します。

- microsoft Defender for Endpoint と Office 365 の Microsoft Defender 間のデータカバレッジが向上し、インシデント管理、自動調査、修復、予防的または事後対応的な脅威検出をドメイン全体で可能にしています。 
- Office 365 用の Microsoft Defender からのメール関連の検出と軽減策、および Microsoft Defender for Endpoint から既に利用できるエンドポイント データ。
- Microsoft Defender for Endpoint と Office 365 用 Microsoft Defender を通してアラートをエンドツーエンドの攻撃ストーリーに集約し、作業キューを削減し、調査を簡素化して高速化する脅威関連インシデントのビュー。
- Microsoft 365 Defender ソリューションによって攻撃の試行が検出およびブロックされました。 また、さらなる露出のリスクを軽減し、回復性を高める予防措置を実行するために使用できるデータがあります。 
- アクション可能な情報をスポットライトに表示する高度な設計により、レポートに緊急に焦点を当て、調査し、活用するデータをすばやく識別できます。

## <a name="a-centralized-learning-hub"></a>集中型学習ハブ

Microsoft 365 セキュリティ センターには、Microsoft セキュリティ ブログ、YouTube の Microsoft セキュリティ コミュニティ、docs.microsoft.com の公式ドキュメントなどのリソースからの公式なガイダンスをバブルアップする学習ハブが含まれています。

学習ハブ内では、Email & Collaboration (Microsoft Defender for Office 365 または MDO) のガイダンスは、Endpoint (Microsoft Defender for Endpoint または MDE) および Microsoft 365 Defender のラーニング リソースと並べて提供されています。

学習ハブが開き、「Microsoft 365 Defender を使用して調査する方法」などのトピックに関するラーニング パスが表示されます。 「Microsoft Defender for Office 365 ベスト プラクティス」を参照してください。 このセクションは現在、Microsoft 内のセキュリティ製品グループによって管理されています。 各ラーニング パスには、概念を理解するために要する時間が反映されます。 たとえば、「Office 365 ユーザー アカウント用の Microsoft Defender が侵害された場合に実行する手順」は、8 分かかると投影され、オンザフライで有益な学習を行います。

コンテンツをクリックすると、このサイトをブックマークし、ブックマークを 'Security' フォルダーまたは 'Critical' フォルダーに整理すると便利な場合があります。 すべてのラーニング パスを表示するには、メイン パネルの [すべてのパスを表示] リンクをクリックします。

> [!NOTE]
> Microsoft 365 セキュリティ センターラーニング ハブの上部には、製品 (現在は Microsoft 365 Defender、エンドポイント用 Microsoft Defender、および Office 365 用の Microsoft Defender) を選択できる便利なフィルターがあります。  各セクションの学習リソースの数が一覧表示されています。これは、トレーニングと学習のために、学習者が用意しているリソースの数を追跡するのに役立ちます。
>
> 製品フィルターと共に、現在のトピック、リソースの種類 (ビデオからウェビナーまで)、セキュリティ領域に関する経験や経験のレベル、セキュリティ ロール、製品機能を示します。

## <a name="send-us-your-feedback"></a>フィードバックをお送りください

フィードバックが必要です。 We're always looking to improve, so if there's there's like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).

また、この記事のフィードバックを送信できます。 In the 'Feedback' section at the end under 'Submit and view feedback', the options are *This product*, or *This page*.

製品のフィードバック **には、この製品** ボタン *を使用* します。

1. 記事 *の下部にある* [この製品] を選択します。
    1. これらの指示を読み続ける場合は、ボタンを右クリックし、[新しいタブで開く] をクリックします。
2. UserVoice フォーラム **に移動します**。
3. 次の 2 つのオプションがあります。
    1. テキスト ボックスまで下にスクロールして、コンプライアンスを改善したり *、Office 365* でユーザーを保護したりするには *、Microsoft 365* セキュリティ センターに貼り付けます。 You can search the results for an idea like yours and up-vote it, or use the button for **Post a new idea**.
    1. この問題が既に報告され、投票 (または投票) でプロファイルを上げる場合は、UserVoiceの右側にある [フィードバックの送信] ボックスを使用します。 Microsoft *365 セキュリティ* センターを検索し、問題を見つけて、投票ボタンを使用して状態を上げてください。

この *ページは、* 記事自体に関するフィードバックに使用します。 フィードバックをお寄せいただきありがとうございます。 お客様の声は、製品の改善に役立ちます。

### <a name="explore-what-the-security-center-has-to-offer"></a>セキュリティ センターが提供する機能を確認する

Microsoft 365 セキュリティ センターの機能を常に確認してください。

- [インシデントとアラートを管理する](manage-incidents.md)
- [脅威分析による新たな脅威の追跡と対応](threat-analytics.md)
- [アクション センター](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [デバイス、メール、アプリ、ID 間で脅威を検出する](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [カスタム検出ルール](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [電子メール&コラボレーションアラート](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [フィッシング攻撃シミュレーションを作成し、](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training)[チームをトレーニングするペイロードを作成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>関連情報
- [Microsoft 365 セキュリティ センター](overview-security-center.md)
- [Microsoft 365 Office 365 用 Microsoft Defender](microsoft-365-security-center-mdo.md)
- [Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [エンドポイント用 Microsoft Defender から Microsoft 365 セキュリティ センターへのアカウントのリダイレクト](microsoft-365-security-mde-redirection.md)
