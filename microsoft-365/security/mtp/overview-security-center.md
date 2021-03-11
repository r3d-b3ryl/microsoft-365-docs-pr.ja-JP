---
title: Microsoft 365 セキュリティ センターの概要
description: Microsoft 365 セキュリティ センターの利点は、Microsoft Defender for Office 365 (MDO) と Microsoft Defender for Endpoint (MDE) と Microsoft Defender for Identity (MDI) と Microsoft Cloud App Security (MCAS) の組み合わせです。 この記事では、管理者向け Microsoft 365 セキュリティ センターの概要を説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、監視、レポート、ID、データ、デバイス、アプリ
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
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 87149ab9c99168d62f5114555a46b8bfaee83ab2
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712104"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>統合された Microsoft 365 セキュリティ センターの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender for Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> Microsoft 365 Defender を体験してみませんか? ラボ環境 [で評価したり、パイロット](https://aka.ms/mtp-trial-lab) プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。

強化された **Microsoft 365** セキュリティ センター ( ) は、電子メール、コラボレーション、ID、およびデバイスの脅威に対する保護、検出、調査、および応答を中央ポータルに [https://security.microsoft.com](https://security.microsoft.com) 組み合わせたものになります。    

Microsoft 365 セキュリティ センターは、Microsoft Defender セキュリティ センターや Office 365 セキュリティ & コンプライアンス センターなど、既存の Microsoft セキュリティ ポータルの機能を統合します。 セキュリティ センターでは、情報への迅速なアクセス、レイアウトの簡易性、関連情報のまとめを重視し、使いやすくしています。 このセンターには、次の情報が含まれます。

- **[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender for Office 365 は、組織が電子メールを保護し、365 リソースを保護するための一連の予防、検出、調査、およびOfficeを支援します。
- **[Microsoft Defender for Endpoint は](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** 、組織内のデバイスに対する予防保護、侵害後の検出、自動調査、および対応を提供します。
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** は、Microsoft 365 セキュリティ ポートフォリオを活用してドメイン全体の脅威データを自動的に分析し、1 つのダッシュボードに対する攻撃の画像を作成する Microsoft の拡張検出および応答 (XDR) ソリューションの一部です。 

コンプライアンス センターまたは Microsoft Defender セキュリティ センター Office 365 セキュリティ &変更点に関する情報が必要な場合は、以下を参照してください。

- [Microsoft 365 セキュリティ センターの Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 セキュリティ センターの Defender for Endpoint](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>何を期待する

Office 365 セキュリティ とコンプライアンス センター (protection.office.com) と Microsoft Defender セキュリティ センター (securitycenter.microsoft.com) で使用するセキュリティ コンテンツはすべて *、Microsoft 365* セキュリティ センターにあります。

Microsoft 365 セキュリティ センターは、セキュリティ チームがさまざまなワークロードからの信号を単一の統合エクスペリエンスに収め、攻撃を調査して対応するのに役立ちます。

- インシデント&アラート
- ハンティング
- アクション センター
- 脅威の分析

Microsoft 365 セキュリティ センターでは、Microsoft Defender for Office 365 と Microsoft Defender for Endpoint が統合され、統一性、明快さ、共通の目標が強調されています。 マージは、以下に示す優先順位に基づいて行われたので、各セキュリティ スイートが組み合わせに持ち込んだ機能を犠牲にすることなく行いました。

- 共通の構成要素
- 一般的な用語
- 共通エンティティ
- 他のワークロードとの機能のパリティ

## <a name="unified-investigations"></a>統合された調査

セキュリティ センターを合理化すると、Microsoft 365 組織全体のインシデントを調査する 1 つのウィンドウが作成されます。 主な例は **、Microsoft** 365 セキュリティ センターのクイック 起動のインシデント ノードです。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO の [インシデント] ページ。":::

たとえば、重大度が高いインシデント名をダブルクリックすると、センターを集約する利点を示すページが表示されます。

![複数のエンドポイントでの特権エスカレーションに関する複数ステージのインシデントで、影響を受けたデバイス 16 台と影響を受けたユーザー 9 人が表示されます。](../../media/converged-incident-info-3.png)

> [!TIP]
> [コンバージド **ユーザー]** タブは、お問い合わせを開始する際に役立つ場所です。 この単一ページは、統合ワークロード (Microsoft Defender for Endpoint、Microsoft Defender for Identity、MCAS を活用している場合) と、オンプレミスの Active Directory、Azure Active Directory、同期、ローカル、サード パーティのユーザーなどのさまざまなソースからの情報を表示します。 新しいユーザー [エクスペリエンスの詳細については、以下を参照してください](investigate-users.md)。

インシデント情報には、影響を受けるメールボックスの横に、ユーザー/ID 固有のデバイスと危険にさらされているデバイスが表示されます。 また、調査情報と **収集された** 証拠も関連 **付けされます**。 これにより、管理者とセキュリティ操作チームは、リスクの高い 1 つのアラートから影響を受けるユーザーやメールボックスに簡単にピボットできます。 このページの上部にある **[インシデント** ] タブを見て、この 1 つの場所から使用できる他の重要なセキュリティ ピボットがあります。

> [!IMPORTANT]
> 特定のインシデントの任意のページの上部に、[概要]、[通知]、[デバイス]、[ユーザー]、[メールボックス]、[調査]、および [証拠] タブが **表示** されます。 

[調査 **] を選択** すると、分析のグラフィックが表示されたページが開き、修復の状態 (保留中の **承認など)** が一覧表示されます。 環境内の特定のインシデントを選択し、これらのタブをドリルダウンし、さまざまな種類の脅威のプロファイルを作成する方法を時間を取ります。 慣れ親しみは、後で迫った調査の恩恵を受けるでしょう。

## <a name="improved-processes"></a>プロセスの改善

共通のコントロールとコンテンツは、同じ場所に表示されるか、データの 1 つのフィードに凝縮され、見つけやすくなります。 たとえば、統合された設定です。

### <a name="unified-settings"></a>統合設定

![[役割] をクリックし、[設定] ページを開きます。これには、全般設定、アクセス許可、API、ルールが含まれます。 [アクセス許可] を開き、[役割] を開きます。 すべての役割を表示する](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>ロール&アクセス許可

![[アクセス許可&グループ、役割、デバイス グループ&エンドポイントの役割を示す [役割] ページ。](../../media/converged-roles-5.png)

 Access the Microsoft 365 security center is configured with Azure Active Directory global roles or using custom roles. Defender for Endpoint については、「ユーザー アクセスを Microsoft Defender セキュリティ センターに割り [当てる」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access)。 Defender for Office 365 については [、「Microsoft 365](../office-365-security/permissions-microsoft-365-compliance-security.md)コンプライアンス センターのアクセス許可」および「Microsoft 365 セキュリティ センター」を参照してください。

- [Microsoft 365 Defender へのアクセスを管理する方法の詳細](mtp-permissions.md)
- Microsoft 365 セキュリティ センター [でカスタム](custom-roles.md) ロールを作成する方法の詳細

### <a name="integrated-reports"></a>統合レポート

レポートは、Microsoft 365 セキュリティ センターでも統合されます。 管理者は、一般的なセキュリティ レポートから始め、エンドポイント、電子メール、コラボレーションに関する特定のレポート&できます。 ここでのリンクは、ワークロード構成に基づいて動的に生成されます。

### <a name="quickly-view-your-microsoft-365-environment"></a>Microsoft 365 環境をすばやく表示する

[ **ホーム]** ページには、セキュリティ チームが必要とする一般的なカードの多くが表示されます。 カードとデータの構成は、ユーザー の役割によって異なります。 Microsoft 365 セキュリティ センターは役割ベースのアクセス制御を使用しますので、役割ごとに、毎日のジョブにとってより意味のあるカードが表示されます。  

この一目でわかる情報は、組織内の最新のアクティビティについて把握するのに役立ちます。 Microsoft 365 セキュリティ センターは、さまざまなソースからの信号をまとめ、Microsoft 365 環境の全体像を示します。

カードは次のカテゴリに分類されます。

- **[ID]**- 組織内の ID を監視し、疑わしい動作や危険な動作を追跡します。 [ID 保護の詳細については、次の情報を参照してください](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。
- **データ** - 許可されていないデータ漏えいにつながる可能性があるユーザー アクティビティの追跡に役立ちます。
- **デバイス** - デバイス上のアラート、侵害アクティビティ、その他の脅威に関する最新の情報を取得します。
- **アプリ** - クラウド アプリが組織でどのように使用されているのかについて、分析情報を得る。 [クラウド アプリ セキュリティで検出されたアプリの詳細については、次のページを参照してください](https://docs.microsoft.com/cloud-app-security/discovered-apps)。

## <a name="threat-analytics-with-better-data-coverage"></a>より優れたデータカバレッジを備えた脅威分析
次の Microsoft 365 Defender 脅威分析統合エクスペリエンスを使用して、新たな脅威を追跡して対応します。

- microsoft Defender for Endpoint と Microsoft Defender for Office 365 のデータカバレッジが向上し、インシデント管理、自動調査、修復、およびドメイン全体での予防的または事後的な脅威検出が可能になります。 
- Microsoft Defender for Endpoint から既に利用可能なエンドポイント データに加えて、Office 365 用 Microsoft Defender からの電子メール関連の検出と軽減策。
- Microsoft Defender for Endpoint および microsoft Defender for Office 365 全体のエンドツーエンド攻撃ストーリーにアラートを集約し、作業キューを削減し、調査を簡素化および高速化する脅威関連インシデントのビュー。
- Microsoft 365 Defender ソリューションによって検出およびブロックされた攻撃の試行。 また、さらなる暴露のリスクを軽減し、回復力を高める予防措置を実行するために使用できるデータも用意されています。 
- アクション可能な情報をスポットライトに当てる強化された設計により、レポートに緊急に焦点を当て、調査し、活用するためのデータをすばやく特定できます。

## <a name="a-centralized-learning-hub"></a>集中学習ハブ

Microsoft 365 セキュリティ センターには、Microsoft セキュリティ ブログ、YouTube の Microsoft セキュリティ コミュニティ、docs.microsoft.com の公式ドキュメントなどのリソースからの公式ガイダンスを吹き込む学習ハブが含まれています。

学習ハブ内では、Email & Collaboration (Microsoft Defender for Office 365 または MDO) のガイダンスは、エンドポイント (エンドポイントまたは MDE 用 Microsoft Defender)、および Microsoft 365 Defender ラーニング リソースと並べて行います。

学習ハブが開き、「Microsoft 365 Defender を使用して調査する方法」などのトピックに関するラーニング パスが表示されます。 および "Microsoft Defender for Office 365 ベスト プラクティス"。 このセクションは現在、Microsoft 内のセキュリティ製品グループによって管理されています。 各ラーニング パスには、概念の取得に要する投影時間が反映されます。 たとえば、「Office 365 ユーザー アカウントの Microsoft Defender が侵害された場合に実行する手順」は、8 分かかると見なされ、その際に学習する価値があります。

コンテンツをクリックすると、このサイトをブックマークし、ブックマークを 'Security' または 'Critical' フォルダーに整理すると便利です。 すべてのラーニング パスを表示するには、メイン パネルの [すべて表示] リンクをクリックします。

> [!NOTE]
> Microsoft 365 セキュリティ センターラーニング ハブの上部には、製品 (現在は Microsoft 365 Defender、Microsoft Defender for Endpoint、Microsoft Defender for Office 365) を選択できる便利なフィルターがあります。  各セクションの学習リソースの数が一覧表示され、学習者がトレーニングと学習に必要なリソースの数を追跡するのに役立ちます。
>
> 製品フィルターと共に、現在のトピック、リソースの種類 (ビデオからウェビナーまで)、セキュリティ領域に関する親しみや経験のレベル、セキュリティ ロール、製品機能が一覧表示されます。

## <a name="send-us-your-feedback"></a>フィードバックを送信する

フィードバックが必要です。 常に改善を行う必要がある場合は [、Microsoft 365 Defender](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)フィードバックをお寄せください。

また、この記事からのフィードバックを残す方法があります。 [フィードバックの送信と表示] の最後にある [フィードバック] セクションで、オプションは [この *製品*] または [このページ] *です*。

製品フィードバック **には、[この製品** ] ボタン *を使用* します。

1. 記事 *の下部にある* [この製品] を選択します。
    1. これらの指示を読み続ける場合は、ボタンを右クリックし、[新しいタブで開く] をクリックします。
2. これにより **、UserVoice フォーラムに移動します**。
3. 次の 2 つのオプションがあります。
    1. テキスト ボックスまで下にスクロールする コンプライアンスを改善するか、Office *365* でユーザーを保護するには *、Microsoft 365* セキュリティ センターに貼り付けます。 結果を検索して、自分のようなアイデアを検索して投票するか、新しいアイデアを投稿するボタン **を使用します**。
    1. この問題が既に報告され、投票 (または投票) でプロファイルを上げる場合は、UserVoiceの右側にある [フィードバックの提供] ボックスを使用します。 Microsoft *365 セキュリティ センターを検索* し、問題 **を** 検索し、投票ボタンを使用して状態を上げる。

記事 *自体に* 関するフィードバックについては、このページを使用します。 ご意見ありがとうございます。 お客様の声は、製品の改善に役立ちます。

### <a name="explore-what-the-security-center-has-to-offer"></a>セキュリティ センターが提供する機能を確認する

Microsoft 365 セキュリティ センターの機能を引き続き確認してください。

- [インシデントとアラートの管理](manage-incidents.md)
- [脅威分析による新たな脅威の追跡と対応](threat-analytics.md)
- [アクション センター](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [デバイス、電子メール、アプリ、および ID 間の脅威を検出する](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [カスタム検出ルール](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [メール&コラボレーション通知](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [フィッシング攻撃シミュレーションを作成し、](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training)[チームをトレーニングするペイロードを作成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>関連情報
- [Microsoft 365 セキュリティ センター](overview-security-center.md)
- [Microsoft 365 セキュリティ Office 365 の Microsoft Defender](microsoft-365-security-center-mdo.md)
- [Microsoft 365 セキュリティ センターのエンドポイント用 Microsoft Defender](microsoft-365-security-center-mde.md)
- [Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターへのアカウントのリダイレクト](microsoft-365-security-mde-redirection.md)
