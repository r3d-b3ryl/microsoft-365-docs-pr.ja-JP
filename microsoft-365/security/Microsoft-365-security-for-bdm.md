---
title: Microsoft 365意思決定者向けセキュリティ (BDM)
description: 組織が現在直面している最も一般的な脅威と攻撃のシナリオは、Microsoft 365、これらのリスクを軽減するための推奨されるアクションです。
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.prod: m365-security
ms.technology: m365d
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.openlocfilehash: 59b74fdc13cc21f0266e0f110935f76656827f65
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63755166"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365意思決定者向けセキュリティ (BDM)

この記事では、組織が現在、Microsoft 365 環境で直面している最も一般的な脅威と攻撃のシナリオと、これらのリスクを軽減するための推奨されるアクションについて説明します。 Microsoft 365には、事前に構成されたさまざまなセキュリティ機能が付属しますが、クラウド サービスにアクセスするために使用される独自の ID、データ、およびデバイスをセキュリティで保護する責任を負う必要もあります。 このガイダンスは、Kozeta Beam (Microsoft Cloud Security Architect) と Thiagaraj Sundararajan (Microsoft シニア コンサルタント) によって開発されました。

この記事は、テナント、電子メール、および SharePoint など、最も重要なサービスと資産の管理に使用されるアカウントの保護を始め、作業の優先順位によって整理されています。 これは、セキュリティにアプローチするための方法を提供し、次のスプレッドシートと一緒に動作し、組織内の関係者やチームとの進捗状況を追跡することができます。[BDMs](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx) スプレッドシートのMicrosoft 365セキュリティ。

:::image type="content" source="../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png" alt-text="BDM セキュリティ推奨事項Microsoft 365の例" lightbox="../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png":::

Microsoft は、テナント内の Secure Score ツールを提供し、通常のアクティビティに基づいてセキュリティの態勢を自動的に分析し、スコアを割り当て、セキュリティ改善の推奨事項を提供します。 この記事で推奨されるアクションを実行する前に、現在のスコアと推奨事項に注意してください。 この記事で推奨されるアクションは、スコアを増やします。 目標は、最大スコアを達成するのではなく、ユーザーの生産性に悪影響を及ぼさない方法で環境を保護する機会を認識する方法です。 「 [Microsoft Secure Score」を参照してください](defender/microsoft-secure-score.md)。

:::image type="content" source="../media/security/security-for-bdms-overview.png" alt-text="ビジネス環境保護対策を提供する Secure Score ツールの例を、Microsoft 365 Defenderします。" lightbox="../media/security/security-for-bdms-overview.png":::

始める前にもう 1 つ。 . . 監査ログ [を有効にしてください](../compliance/search-the-audit-log-in-security-and-compliance.md)。 インシデントや侵害を調査する必要がある場合は、後でこのデータが必要になります。

## <a name="protect-privileged-accounts"></a>特権アカウントの保護

最初の手順として、これらのアカウントには重要なサービスとリソースを管理および変更するためのアクセス権とアクセス許可が付与され、侵害された場合に組織全体に悪影響を及ぼす可能性があるので、環境内の重要なアカウントに保護の層を追加することをお勧めします。 特権アカウントの保護は、侵害されたアカウントのアクセス許可を管理アカウントに昇格する攻撃者から保護する最も効果的な方法の 1 つです。

|推奨事項  |E3 |E5  |
|---------|---------|---------|
|すべての管理アカウントに対して多要素認証 (MFA) を適用します。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|クライアントAzure Active Directory (Azure AD) Privileged Identity Management (PIM) を実装して、特定のリソースと Azure リソースに just-in-time 特権アクセスAzure AD適用します。 また、アクセス権を持つユーザーを検出し、特権アクセスを確認できます。|         | ![緑色のチェック マーク。](../media/green-check-mark.png)|
|特権アクセス管理を実装して、特権管理タスクに対する詳細なアクセス制御を管理Office 365。 |         | ![緑色のチェック マーク。](../media/green-check-mark.png)|
|サービスを管理するには、特権アクセス ワークステーション (PAW) を構成して使用します。 インターネットを閲覧し、管理アカウントに関連しない電子メールを確認する場合は、同じワークステーションを使用しない。|  !![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)::: |

次の図は、これらの機能を示しています。
:::image type="content" source="../media/m365-security-bdm-illustrations-privileged-accounts.png" alt-text="特権アカウントを保護するためのツールによって提供される機能の例" lightbox="../media/m365-security-bdm-illustrations-privileged-accounts.png":::

追加の推奨事項:

- オンプレミスから同期されるアカウントに、クラウド サービスの管理者ロールが割り当てられていないか確認します。 これにより、攻撃者がオンプレミス アカウントを適用してクラウド サービスへの管理アクセスを取得するのを防ぐのに役立ちます。
- サービス アカウントに管理者ロールが割り当てられていないか確認します。 多くの場合、これらのアカウントは監視され、有効期限が切れないパスワードで設定されます。 まず、AADConnect および ADFS サービス アカウントが既定でグローバル管理者ではないか確認します。
- 管理者アカウントからライセンスを削除します。 特定の管理者アカウントにライセンスを割り当てる特定の使用例がない限り、これらのアカウントからライセンスを削除します。

## <a name="reduce-the-surface-of-attack"></a>攻撃の表面を減らす

次のフォーカス領域は、攻撃の表面を減らすことです。 これは、ユーザーとサービスへの最小限の労力と影響で実現できます。 攻撃の表面領域を減らすことで、攻撃者は組織に対して攻撃を開始する方法が少なくなっています。

次に、いくつかの例を示します:

- POP3、IMAP、および SMTP プロトコルを無効にします。 最新のほとんどの組織では、これらの古いプロトコルは使用されなくなりました。 これらを安全に無効にし、必要に応じて例外のみを許可できます。
- テナント内のグローバル管理者の数を最小限に抑えます。 これにより、すべてのクラウド アプリケーションの攻撃領域が直接減少します。
- 環境で使用されなくなったサーバーとアプリケーションを廃止します。
- 使用されなくなったアカウントを無効にして削除するためのプロセスを実装します。

## <a name="protect-against-known-threats"></a>既知の脅威から保護する

既知の脅威には、マルウェア、侵害されたアカウント、フィッシングが含まれます。 これらの脅威に対する一部の保護は、ユーザーに直接影響を与え、迅速に実装できる一方で、より多くの計画とユーザートレーニングが必要な場合もあります。

|推奨事項  |E3  |E5  |
|---------|---------|---------|
|**多要素認証をセットアップし、サインイン リスク ポリシーを含む推奨条件付きアクセス ポリシーを使用します**。 Microsoft では、すべてのクラウド アプリを保護するために一緒に動作する一連のポリシーを推奨し、テストしました。Office 365およびMicrosoft 365しています。 「 [Identity and device access configurations」を参照してください](./office-365-security/microsoft-365-policies-configurations.md)。 | |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**すべてのユーザーに多要素認証が必要です**。 推奨される条件付きアクセス ポリシーを実装するために必要なライセンスが必要ない場合は、少なくともすべてのユーザーに多要素認証が必要です。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**メール内のマルウェアに対する保護のレベルを上げる**。 マルウェアOffice 365またはMicrosoft 365環境にはマルウェアに対する保護が含まれますが、マルウェアに一般的に使用されるファイルの種類を含む添付ファイルをブロックすることで、この保護を強化できます。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**標的型フィッシング攻撃からメールを保護します**。 1 つ以上のカスタム ドメインを Office 365または Microsoft 365環境に構成した場合は、ターゲットフィッシング対策保護を構成できます。 Office 365 の Defender の一部であるフィッシング対策保護は、悪意のある偽装ベースのフィッシング攻撃や他のフィッシング攻撃から組織を保護するのに役立ちます。 カスタム ドメインを構成していない場合は、これを行う必要があります。| |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**電子メールでのランサムウェア攻撃から保護します**。 ランサムウェアは、ファイルを暗号化したり、コンピューターの画面をロックしたりして、データへのアクセスを取り去る。 その後、データへのアクセスを返すのと引き換えに、通常はBitcoinのような暗号化の形で「身代金」を求め、被害者から金銭を強要しようとする。 1 つ以上のメール フロー ルールを作成して、ランサムウェアに一般的に使用されるファイル拡張子をブロックしたり、電子メールでこれらの添付ファイルを受け取るユーザーに警告したりすることで、ランサムウェアからの防御を支援できます。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**ビジネスを行う国からの接続をブロックします**。 これらの国Azure AD接続をブロックする条件付きアクセス ポリシーを作成し、テナントの周囲に地理的ファイアウォールを効果的に作成します。| |![緑色のチェック マーク。](../media/green-check-mark.png)|

次の図は、これらの機能を示しています。
:::image type="content" source="../media/m365-security-bdm-illustrations-known-threats.png" alt-text="さまざまな種類の脅威から保護するためのツールによって提供されるさまざまな機能の例" lightbox="../media/m365-security-bdm-illustrations-known-threats.png":::

## <a name="protect-against-unknown-threats"></a>未知の脅威から保護する

特権アカウントに追加の保護を追加し、既知の攻撃から保護した後、未知の脅威からの保護に注意を移してください。 より決定された高度な敵対者は、組織を攻撃するために革新的で新しい未知の方法を使用します。 Microsoft は、数十億を超えるデバイス、アプリケーション、およびサービスを収集した膨大なデータを使用して、Windows、Office 365、Azure で Office 365 の Defender を実行して、Zero-Day 攻撃を防止し、砂箱環境を利用し、コンテンツへのアクセスを許可する前に有効性を確認することができます。

|推奨事項  |E3  |E5  |
|---------|---------|---------|
|**Microsoft Defender for Office 365**:<br>*セーフ添付ファイル<br>* セーフリンク    <br>*Microsoft Defender for Endpoint for SharePoint、<br>* OneDrive、Microsoft Teams保護のための Defender でのフィッシングOffice 365防止|         |![緑色のチェック マーク。](../media/green-check-mark.png) |
|**Microsoft Defender for Endpoint の機能を構成します**。<br>*<br>Windows Defender ウイルス対策* エクスプロイト保護 <br> *攻撃表面の縮小 <br>*    ハードウェア ベースの分離 <br>* フォルダー アクセスの制御     |         |![緑色のチェック マーク。](../media/green-check-mark.png) |
|**Microsoft Defender for Cloud Apps を使用して** SaaS アプリを検出し、動作分析と異常検出の使用を開始します。 |         |![緑色のチェック マーク。](../media/green-check-mark.png) |

次の図は、これらの機能を示しています。
:::image type="content" source="../media/m365-security-bdm-illustrations-unknown-threats.png" alt-text="未知の脅威から保護するためのツールによって提供される機能の例" lightbox="../media/m365-security-bdm-illustrations-unknown-threats.png":::

追加の推奨事項:

- TLS を使用したメールのようなパートナー チャネル通信をセキュリティで保護します。
- 通信Teamsパートナーにのみフェデレーションを開きます。
- 送信者ドメイン、個々の送信者、または送信元 IP を許可リストに追加しない。これにより、スパムやマルウェアのチェックをバイパスできます。一般的な方法として、ユーザーが独自の受け入れドメインや、電子メール フローの問題が許可リストに報告されている可能性のある他の多くのドメインを追加する方法があります。 [スパムと接続フィルター] ボックスの一覧にドメインを追加しない場合は、すべてのスパム チェックがバイパスされる可能性があります。
- 送信スパム通知を有効にする - 内部ユーザーが外部からスパムメールを送信している場合に、ヘルプデスクまたは IT 管理者チームに内部的に配布リストへの送信スパム通知を有効にします。 これは、アカウントが侵害されたというインジケーターである可能性があります。
- すべてのユーザーに対してリモート PowerShell を無効にします。リモート PowerShell は主に管理者が管理目的またはプログラムによる API アクセスのためにサービスにアクセスするために使用されます。 管理者以外のユーザーがアクセスするビジネス要件がない限り、管理者以外のユーザーに対してこのオプションを無効にし、偵察を避けることをお勧めします。
- 管理者以外のすべての管理者Microsoft Azure管理ポータルへのアクセスをブロックします。 これを行うには、管理者を除くすべてのユーザーをブロックする条件付きアクセス ルールを作成します。

## <a name="assume-breach"></a>違反を想定する

Microsoft は、脅威や攻撃を防止するためにあらゆる手段を講じながら、常に "違反を想定する" 考え方で作業することをお勧めします。 攻撃者が何とか環境に侵入した場合でも、攻撃者が環境からデータや ID 情報を引き出さなくてもいいです。 このため、社会保障番号、クレジット カード番号、その他の個人情報、その他の組織レベルの機密情報などの機密データ漏洩に対する保護を有効にすることをお勧めします。


|推奨事項 |E3|E5 |
|---------|---------|---------|
|**条件付きアクセスと関連するポリシー** を確認して最適化し、ゼロトラスト ネットワークの目標に合わせて調整します。 既知の脅威からの保護には、一連の推奨ポリシー [の実装が含まれます](./office-365-security/microsoft-365-policies-configurations.md)。 これらのポリシーの実装を確認して、ネットワークにアクセスしたハッカーからアプリとデータを保護します。 推奨される Intune アプリ保護ポリシーは、Windows 10保護Windows (WIP) を有効にします。 WIP は、電子メール、ソーシャル メディア、パブリック クラウドなど、アプリやサービスを通じて組織データが偶発的に漏洩しないように保護します。 |         |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**外部メール転送を無効にします**。 ユーザーのメールボックスにアクセスするハッカーは、メールを自動的に転送するメールボックスを設定することで、メールを盗む可能性があります。 これは、ユーザーの認識がなくても発生する可能性があります。 メール フロー ルールを構成することで、この問題を回避できます。|![緑色のチェック マーク。](../media/green-check-mark.png) |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**匿名の外部予定表共有を無効にします**。 既定では、外部の匿名予定表の共有が許可されます。 [予定表の共有を無効](/exchange/sharing/sharing-policies/modify-a-sharing-policy) にして、機密情報の潜在的なリークを減らします。|![緑色のチェック マーク。](../media/green-check-mark.png) |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**機密データのデータ損失防止ポリシーを構成します**。 セキュリティ コンプライアンス センターでデータ &amp; 損失防止ポリシーを作成し、クレジット カード番号、社会保障番号、銀行口座番号などの機密データを検出して保護します。 Microsoft 365には、データ損失防止ポリシーで使用できる多くの定義済みの機密情報の種類が含まれています。 また、環境に合った機密データ用に独自の機密情報の種類を作成することもできます。 |![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**データ分類と情報保護ポリシーを実装します**。 機密ラベルを実装し、これらを使用して機密データを分類して保護を適用します。 これらのラベルは、データ損失防止ポリシーでも使用できます。 Azure Information Protection ラベルを使用している場合は、他の管理センターで新しいラベルを作成しないようにすることをお勧めします。|         |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**Defender for Cloud Apps を使用して、サード パーティ製のアプリとサービスのデータを保護します**。 Defender for Cloud Apps ポリシーを構成して、Salesforce、Box、クラウド アプリケーションなどのサードパーティのクラウド アプリ全体で機密情報を保護Dropbox。 Defender for Cloud Apps ポリシーで作成した機密情報の種類と機密ラベルを使用して、SaaS アプリ全体に適用できます。 <br><br>Microsoft Defender for Cloud Apps を使用すると、さまざまな自動化プロセスを適用できます。 ポリシーは、継続的なコンプライアンス スキャン、法的な電子情報開示タスク、公開で共有される機密性の高いコンテンツの DLP を提供するために設定できます。 Defender for Cloud Apps では、20 を超えるメタデータ フィルター (アクセス レベル、ファイルの種類など) に基づいて、任意の種類のファイルを監視できます。 |         |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**[Microsoft Defender for Endpoint を使用して](/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview)、ユーザーが** 自分のデバイスに機密情報を保存Windowsします。 |         |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**[AIP スキャナーを使用して](/azure/information-protection/deploy-aip-scanner)、サーバーとファイル共有全体の情報を識別および分類します**。 AIP レポート ツールを使用して結果を表示し、適切なアクションを実行します。|         |![緑色のチェック マーク。](../media/green-check-mark.png)|

次の図は、これらの機能を示しています。
![侵害から保護するための推奨機能。](../media/m365-security-bdm-illustrations-assume-breach.png)
:::image type="content" source="../media/m365-security-bdm-illustrations-assume-breach.png" alt-text="侵害から保護するツールによって提供される機能の例" lightbox="../media/m365-security-bdm-illustrations-assume-breach.png":::

## <a name="continuous-monitoring-and-auditing"></a>継続的な監視と監査

最後に、Microsoft 365 環境と Windows およびデバイスの継続的な監視と監査は、侵入を迅速に検出して修復するために重要です。 Secure Score、Microsoft 365 Defender ポータル、Microsoft Intelligent Graph の高度な分析などのツールは、テナントに貴重な情報を提供し、膨大な量の脅威インテリジェンスとセキュリティ データをリンクして、比類のない脅威の保護と検出を提供します。

|推奨事項 |E3 |E5 |
|---------|---------|---------|
|監査ログ **が有効** になっていることを確認します。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**週に 1 回セキュリティ** で保護されたスコアを確認する - セキュリティスコアは、会社のセキュリティ状態にアクセスし、セキュリティスコアの推奨事項に基づいてアクションを実行するための中心的な場所です。 このチェックは毎週実行する必要があります。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|Microsoft **Defender を使用して、次のOffice 365** 使用します。<br>*脅威の調査と対応の機能<br>*    自動調査と対応 |         |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**エンドポイントに Microsoft Defender を使用する**:<br> *[エンドポイントの検出と応答](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br>*    自動調査と修復 セキュア スコア <br>*    [高度な検索](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**Microsoft Defender for Cloud Apps** を使用して、クラウド アプリ全体で異常な動作を検出して、ランサムウェア、侵害されたユーザー、または不正なアプリケーションを特定し、リスクの高い使用状況を分析し、組織のリスクを制限するために自動的に修復します。|         |:::image type="content" source="../media/green-check-mark.png" alt-text="緑色のチェック マークの例" lightbox="../media/green-check-mark.png":::|
|**Microsoft Sentinel または現在** の SIEM ツールを使用して、環境全体の脅威を監視します。 |         |![緑色のチェック マーク。](../media/green-check-mark.png)|
|**[Microsoft Defender for Identity を展開](/azure-advanced-threat-protection/what-is-atp)** して、オンプレミスの Active Directory 環境を対象とした脅威を監視および保護します。   |         |![緑色のチェック マーク。](../media/green-check-mark.png) |
|**Microsoft Defender for Cloud を使用して**、ハイブリッドワークロードとクラウド ワークロード全体の脅威を監視します。 Microsoft Defender for Cloud には、無料の機能層と、リソース時間またはトランザクションに基づいて支払われる標準レベルの機能が含まれています。|         |         |

次の図は、これらの機能を示しています。
:::image type="content" source="../media/m365-security-bdm-illustrations-monitoring-auditing.png" alt-text="脅威の保護と検出を有効にするツールによって提供される機能の例" lightbox="../media/m365-security-bdm-illustrations-monitoring-auditing.png":::

推奨される監視アクションの上位:

- **Microsoft Secure Score を毎週確認** する - Secure score は、テナントのセキュリティ状態にアクセスし、トップ推奨事項に基づいてアクションを実行するための中心的な場所です。 このチェックは毎週実行する必要があります。 セキュリティで保護されたスコアには、Azure AD Intune、Defender for Cloud Apps、Microsoft Defender for Endpoint、および Microsoft Defender for Endpoint の推奨事項が含Office 365。
- **リスクの高いログイン** を毎週確認する - Azure AD管理センターを使用して、リスクの高いサインインを毎週確認します。 推奨される ID およびデバイス アクセス ルール セットには、危険なサインインにパスワード変更を適用するポリシーが含まれています。  
- マルウェア **と** フィッシング詐欺の上位ユーザーを毎週確認する - microsoft Defender for Office 365 Threat Explorer を使用して、マルウェアとフィッシングの対象となった上位ユーザーを確認し、これらのユーザーが影響を受ける理由の根本原因を調べた。
