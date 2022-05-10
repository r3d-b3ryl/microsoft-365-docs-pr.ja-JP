---
title: MDO、MDE、MDI、MCASを組み合わせたMicrosoft 365 Defenderの概要
description: Microsoft Defender for Office 365 (MDO) と Microsoft Defender for Endpoint (MDE) を組み合わせたMicrosoft 365 Defenderの利点と、Microsoft Defender for Identity (MDI) とMicrosoft Cloud App Security (MCAS)。 この記事では、管理者向けのMicrosoft 365 Defenderの進みについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、モニター、レポート、ID、データ、デバイス、アプリ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 04/21/2021
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
ms.openlocfilehash: a0dce3a61847924043a10df4c13c963f279ea011
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717636"
---
# <a name="microsoft-365-defender-overview"></a>Microsoft 365 Defenderの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

> Microsoft 365 Defender を体験しますか? [ラボ環境で評価](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)、または[運用でパイロット プロジェクトを実行](m365d-pilot.md?ocid=cx-evalpilot)することができます。

**Microsoft 365 Defender** ([https://security.microsoft.com](https://security.microsoft.com)) は、*電子メール*、*コラボレーション*、*ID*、*デバイス* の脅威に対する保護、検出、調査、および対応を中央ポータルで組み合わせたものです。

Microsoft 365 Defenderは、Microsoft Defender セキュリティ センターやOffice 365 セキュリティ & コンプライアンス センターなど、既存の Microsoft セキュリティ ポータルから機能をまとめます。 セキュリティ センターは、情報への迅速なアクセス、よりシンプルなレイアウト、およびより簡単に使用できるように関連情報をまとめることを重視しています。 このセンターには次のものが含まれます。

- **[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365 は、メールと Office 365 リソースを保護するための一連の防止、検出、調査、およびハンティング機能を使用して、組織が企業を保護するのに役立ちます。
- **[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** は、組織内のデバイスに対して、予防的な保護、侵害後の検出、自動調査、および対応を提供します。
- **[Microsoft 365 Defender](microsoft-365-defender.md)** は、Microsoft の *Extended Detection and Response* (XDR) ソリューションの一部であり、Microsoft 365 セキュリティ ポートフォリオを活用して、ドメイン全体の脅威データを自動的に分析し、単一のダッシュボードで攻撃の全体像を構築します。

Office 365 セキュリティ/コンプライアンス センターまたは Microsoft Defender セキュリティ センターからの変更点に関する情報が必要な場合は、以下を参照してください。

- [Microsoft 365 Defender の Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender の Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)

> [!NOTE]
> Microsoft 365 セキュリティ ポータルでは、既存のロールベースのアクセスを使用して適用し、各セキュリティ モデルを統合ポータルに移動します。 各収束ワークロードには、独自のロールベースのアクセス権があります。 製品に既に含まれているロールは、Microsoft 365 セキュリティ ポータルに自動的に集約されます。 ただし、MCASのロールとアクセス許可は、MCASで引き続き処理されます。

## <a name="what-to-expect"></a>想定される変化

Office 365 セキュリティとコンプライアンス センター (protection.office.com) と Microsoft Defender セキュリティ センター (securitycenter.microsoft.com) で使用するすべてのセキュリティ コンテンツが *、Microsoft 365 Defender* に表示されるようになりました。

Microsoft 365 Defenderは、さまざまなワークロードからのシグナルを次の統合エクスペリエンスのセットに取り込むことで、セキュリティ チームが攻撃を調査し、対応するのに役立ちます。

- インシデントとアラート
- 検索
- アクション センター
- 脅威の分析

Microsoft 365 Defender は、Microsoft Defender for Office 365 および Microsoft Defender for Endpoint を統合する際に、*統一性、明確性、および共通の目標* を強調しています。 統合は、以下にリストされている優先順位に基づいており、各セキュリティ スイートが以下の組み合わせにもたらした機能を犠牲にすることなく行われました。

- 共通の構築ブロック
- 共通の用語
- 共通のエンティティ
- 他のワークロードと同等の機能

> [!NOTE]
> Microsoft 365 Defenderは、お客様が移行手順を実行したり、新しいライセンスを購入したりする必要なくアクセスできます。 たとえば、この新しいポータルは、プラン 1 およびプラン 2 の管理者と同様に、E3 サブスクリプションを Microsoft Defender for Office 365持つ管理者がアクセスできるようになります。ただし、Exchange Online Protection、またはDefender for Office 365 プラン 1 のお客様には、サブスクリプション ライセンスでサポートされているセキュリティ機能のみが表示されます。 新しいセンターの目標は、セキュリティを一元化することです。

## <a name="unified-investigations"></a>統一された調査

セキュリティ センターを収束すると、Microsoft 365全体のセキュリティ インシデントを調査するための 1 つの場所が作成されます。 主な例は、Microsoft 365 Defender のクイック起動時の **インシデントとアラート** の下の **インシデント** です。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Microsoft 365 Defenderの [インシデント] ページ。":::

インシデント名を選択すると、セキュリティ センターの収束の価値を示すページが表示されます。

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Microsoft 365 Defender のインシデントの [概要] ページの例":::

<!--
![Example of the Summary page for an incident in Microsoft 365 Defender.](../../media/converged-incident-info-3.png)
--> 

インシデント ページの上部に、[**概要**]、[**アラート]**、[**デバイス]**、[**ユーザー]**、[**メールボックス**]、[調査]、[**証拠]** タブ **が** 表示されます。 詳細については、これらのタブを選択してください。 たとえば、[**ユーザー**] タブには、コンバージド ワークロード (Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Cloud App Security) のユーザーの情報と、さまざまなソース (例:オンプレミスの Active Directory Domain Services (AD DS)、Azure Active Directory (Azure AD)、サードパーティ ID プロバイダー。 詳細については、「[ユーザーを調査する](investigate-users.md)」を参照してください。

環境内のインシデントを確認し、これらのタブをドリルダウンし、さまざまな種類の脅威に対してインシデントに提供される情報にアクセスする方法の理解を実践します。

詳細については、「[Microsoft 365 Defender のインシデント](incidents-overview.md)」を参照してください。

## <a name="improved-processes"></a>改善されたプロセス

共通のコントロールとコンテンツは、同じ場所に表示されるか、データの 1 つのフィードにまとめられて、見つけやすくなります。たとえば、統一された設定などです。

### <a name="unified-settings"></a>統一された設定

![[役割] をクリックして、[設定] ページを開きました。このページには、[全般設定]、[アクセス許可]、[API]、および [ルール] が含まれています。 [アクセス許可]、[役割] の順に開きます。 すべてのロールを表示します。](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>アクセス許可と役割

![エンドポイントの役割とグループ、役割、およびデバイス グループを表示する [アクセス許可と役割] ページ。](../../media/converged-roles-5.png)

 Microsoft 365 Defenderへのアクセスは、Azure Active Directoryグローバル ロールまたはカスタム ロールを使用して構成されます。 Defender for Endpoint については、「[Microsoft Defender セキュリティ センターへのユーザー アクセスの割り当て](/microsoft-365/security/defender-endpoint/assign-portal-access)」をご覧ください。 Defender for Office 365 については、「[Microsoft 365 コンプライアンス センターと Microsoft 365 Defender のアクセス許可](../office-365-security/permissions-microsoft-365-compliance-security.md)」をご覧ください。

- [Microsoft 365 Defender へのアクセスを管理する](m365d-permissions.md)方法の詳細
- Microsoft 365 Defender で[カスタム ロールを作成](custom-roles.md)する方法の詳細

> [!NOTE]
> Microsoft 365 DefenderのMicrosoft Defender for Endpointでは、[Microsoft Defender セキュリティ センター](./mssp-access.md)でアクセスが許可されるのと同じ方法で[、マネージド セキュリティ サービス プロバイダー (MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) へのアクセスを許可できます。

### <a name="integrated-reports"></a>統合レポート

レポートは、Microsoft 365 Defender でも統合されます。 管理者は、一般的なセキュリティ レポートから始めて、エンドポイント、メール、コラボレーションに関する特定のレポートに分岐できます。 ここでのリンクは、ワークロード構成に基づいて動的に生成されます。

### <a name="quickly-view-your-microsoft-365-environment"></a>Microsoft 365 環境をすばやく表示する

**ホーム** ページには、セキュリティ チームが必要とする一般的なカードの多くが表示されます。 カードとデータの構成は、ユーザーの役割によって異なります。 Microsoft 365 Defender ポータルは役割ベースのアクセス制御を使用しているため、役割が異なれば、日常業務にとってより意味のあるカードが表示されます。  

この一目でわかる情報は、組織内の最新の活動についていくのに役立ちます。 Microsoft 365 Defender は、さまざまなソースからの信号をまとめて、Microsoft 365 環境の全体像を示します。

カードは次のカテゴリに分類されます。

- **ID** - 組織内の ID を監視し、疑わしいまたは危険な行動を追跡します。[ID 保護の詳細情報](/azure/active-directory/identity-protection/overview-identity-protection)。
- **データ** - 無許可のデータ開示につながる可能性のあるユーザー アクティビティを追跡するのに役立ちます。
- **デバイス** - デバイス上のアラート、違反アクティビティ、およびその他の脅威に関する最新情報を取得します。
- **アプリ** - 組織でクラウド アプリがどのように使用されているかについての分析情報を得ます。 [Cloud App Security で検出されたアプリの詳細をご覧ください](/cloud-app-security/discovered-apps)。

## <a name="threat-analytics-with-better-data-coverage"></a>より優れたデータ カバレッジを備えた脅威の分析
次の Microsoft 365 Defender 脅威分析統合エクスペリエンスを使用して、新たな脅威を追跡し、対応します。

- Microsoft Defender for Endpoint と Microsoft Defender for Office 365 の間のデータ カバレッジが向上し、インシデント管理、自動調査、修復、およびドメイン全体での予防的または事後対応的な脅威ハンティングの組み合わせが可能になります。 
- Microsoft Defender for Endpoint から既に利用可能なエンドポイント データに加えて、Microsoft Defender for Office 365 からのメール関連の検出と軽減。
- Microsoft Defender for Endpoint と Microsoft Defender for Office 365 全体のエンドツーエンドの攻撃ストーリーにアラートを集約して、作業キューを削減し、調査を簡素化および高速化する、脅威関連のインシデントのビュー。
- Microsoft 365 Defender ソリューションによって検出され、ブロックされた攻撃の試み。 さらなる曝露のリスクを軽減し、回復力を高める予防措置を推進するために使用できるデータもあります。 
- 実用的な情報にスポットライトを当て、緊急に焦点を合わせ、調査し、レポートから活用するデータをすばやく特定できるようにする拡張された設計。

## <a name="a-centralized-learning-hub"></a>一元化されたラーニング ハブ

Microsoft 365 Defender ポータルには、Microsoft セキュリティ ブログ、YouTube の Microsoft セキュリティ コミュニティ、docs.microsoft.com の公式ドキュメントなどのリソースから公式ガイダンスを作成するラーニング ハブが含まれています。

ラーニング ハブ内では、メールとコラボレーション (Microsoft Defender for Office 365) のガイダンスが、Endpoint (Microsoft Defender for Endpoint) および Microsoft 365 Defender ラーニング リソースと並んでいます。

ラーニング ハブは、「Microsoft 365 Defender を使用して調査する方法」 および「Microsoft Defender for Office 365 のベスト プラクティス」などのトピックを中心に編成されたラーニング パスで始まります。 このセクションは現在、Microsoft 内のセキュリティ製品グループによってキュレーションされています。 各ラーニング パスは、概念を理解するのにかかると予想される時間を反映しています。 たとえば、「Microsoft Defender for Office 365 ユーザー アカウントが侵害された場合の手順」は 8 分かかると予想されており、その場で学ぶ価値があります。

コンテンツをクリックした後、このサイトをブックマークして、ブックマークを 'セキュリティ' または 'クリティカル' フォルダーに整理すると便利な場合があります。 すべてのラーニング パスを表示するには、メイン パネルの [すべて表示] リンクをクリックします。

> [!NOTE]
> Microsoft 365 Defender のラーニング ハブの上部には、製品 (現在、Microsoft 365 Defender、Microsoft Defender for Endpoint、および Microsoft Defender for Office 365) から選択できる便利な **フィルター** があります。 各セクションの学習リソースの数がリストされていることに注意してください。これは、学習者がトレーニングと学習のために手元にあるリソースの数を追跡するのに役立ちます。
>
> 製品フィルターに沿って、現在のトピック、リソースの種類 (ビデオからウェビナーまで)、セキュリティ領域に関する知識または経験のレベル、セキュリティの役割、および製品の機能が一覧表示されます。

> [!TIP]
> [Microsoft Learn](/learn/) には、他にも多くの学習機会があります。 [コース MS-500T02-A: Microsoft 365 脅威に対する保護の実装](/learn/certifications/courses/ms-500t02)などといった認定トレーニングがあります。

## <a name="send-us-your-feedback"></a>フィードバックの送信

フィードバックをお寄せください。 私たちは常に改善を目指しています。ご要望がありましたら、[Microsoft 365 Defender のフィードバックを送信してください](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。

この記事からフィードバックを残すこともできます。[フィードバックの送信と表示] の下の最後にある [フィードバック] セクションのオプションは、*[この製品]*、または *[このページ]* です。

*製品* のフィードバックには、**[この製品]** ボタンを使用してください。

1. 記事の下部にある *[この製品]* を選択します。
    1. これらの指示を読み続ける場合は、ボタンを右クリックして [新しいタブで開く] を選択してください。
2. これにより、**UserVoice フォーラム** に移動します。
3. 2 つのオプションがあります。
    1. テキスト ボックス「*Office 365 でコンプライアンスを改善したり、ユーザーをより適切に保護するにはどうすればよいですか?*」まで下にスクロールして、*Microsoft 365 Defender* に貼り付けます。 結果から自分のようなアイデアを探して賛成票を投じるか、**[新しいアイデアを投稿する]** ボタンを使用できます。
    1. この問題がすでに報告されていると確信し、1 票または複数の票でそのプロファイルを上げたい場合は、UserVoice の右側にある *[フィードバックの送信]* ボックスを使用してください。 ｊい *Microsoft 365 Defender* を検索して、**問題を見つけ、投票ボタンを使用** して、その状態を引き上げます。

記事自体に関するフィードバックは、*[このページ]* を使用してください。 フィードバックしていただき、ありがとうございます。 あなたの声は製品の改善に役立ちます。

### <a name="explore-what-the-security-center-has-to-offer"></a>セキュリティ センターが提供するものを調べる

Microsoft 365 Defender の機能を引き続き確認します。

- [インシデントとアラートを管理する](manage-incidents.md)
- [脅威の分析を使用して、新たな脅威を追跡し対応する](threat-analytics.md)
- [アクション センター](m365d-action-center.md)
- [デバイス、メール、アプリ、ID 全体の脅威を探す](./advanced-hunting-query-emails-devices.md)
- [カスタム検出ルール](./custom-detection-rules.md)
- [メールとコラボレーションのアラート](../../compliance/alert-policies.md#default-alert-policies)
- [フィッシング攻撃のシミュレーションを作成し](../office-365-security/attack-simulation-training.md)、[チームをトレーニングするためのペイロードを作成する](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>関連情報
- [Microsoft 365 Defender の Microsoft Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender の Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [Microsoft Defender for EndpointからMicrosoft 365 Defenderへのアカウントのリダイレクト](microsoft-365-security-mde-redirection.md)