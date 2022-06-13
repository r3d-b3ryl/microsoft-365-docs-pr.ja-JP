---
title: ビジネス意思決定者 (BDM) のセキュリティをMicrosoft 365する
description: 組織がMicrosoft 365環境で現在直面している最も一般的な脅威と攻撃のシナリオと、これらのリスクを軽減するための推奨されるアクション。
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
ms.openlocfilehash: 056244562191389ee0991ef1040348ef5e6f82f7
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66015398"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>ビジネス意思決定者 (BDM) のセキュリティをMicrosoft 365する

この記事では、組織のMicrosoft 365環境で現在直面している最も一般的な脅威と攻撃のシナリオと、これらのリスクを軽減するための推奨されるアクションについて説明します。 Microsoft 365には、事前に構成されたさまざまなセキュリティ機能が用意されていますが、クラウド サービスにアクセスするために使用される独自の ID、データ、デバイスをセキュリティで保護する責任も顧客として必要です。 このガイダンスは、Kozeta Beam (Microsoft Cloud Security Architect) と Thiagaraj Sunstructurerajan (Microsoft シニア コンサルタント) によって開発されました。

この記事は、テナント、電子メール、SharePointなど、最も重要なサービスや資産の管理に使用されるアカウントを保護することから始めて、作業の優先順位によって整理されています。 これにより、セキュリティにアプローチするための方法が提供され、次のスプレッドシートと連携して、組織全体の関係者やチームとの進捗状況を追跡できます。[BDMs スプレッドシートのセキュリティMicrosoft 365](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)。

:::image type="content" source="../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png" alt-text="Microsoft 365 BDM セキュリティに関する推奨事項のスプレッズシートの例" lightbox="../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png":::

Microsoft では、テナント内にセキュリティ スコア ツールを提供し、通常のアクティビティに基づいてセキュリティ体制を自動的に分析し、スコアを割り当て、セキュリティ強化の推奨事項を提供します。 この記事で推奨されているアクションを実行する前に、現在のスコアと推奨事項をメモしておきます。 この記事で推奨されるアクションにより、スコアが向上します。 目標は、最大スコアを達成することではなく、ユーザーの生産性に悪影響を及ぼさない方法で環境を保護する機会を認識することです。 [Microsoft セキュリティ スコアを](defender/microsoft-secure-score.md)参照してください。

:::image type="content" source="../media/security/security-for-bdms-overview.png" alt-text="ビジネスに対するリスクを軽減する手順" lightbox="../media/security/security-for-bdms-overview.png":::

作業を開始する前にもう 1 つ. . . [必ず監査ログを有効にしてください](../compliance/search-the-audit-log-in-security-and-compliance.md)。 インシデントまたは違反を調査する必要がある場合は、後でこのデータが必要になります。

## <a name="protect-privileged-accounts"></a>特権アカウントを保護する

最初の手順として、環境内の重要なアカウントに、重要なサービスやリソースを管理および変更するためのアクセス許可とアクセス許可があるため、セキュリティが侵害された場合に組織全体に悪影響を及ぼす可能性があるため、環境内の重要なアカウントに追加の保護レイヤーが与えられていることを確認することをお勧めします。 特権アカウントを保護することは、侵害されたアカウントのアクセス許可を管理アカウントに昇格させようとする攻撃者から保護する最も効果的な方法の 1 つです。

|推奨事項|E3|E5|
|---|---|---|
|すべての管理アカウントに多要素認証 (MFA) を適用します。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|Azure Active Directory (Azure AD) Privileged Identity Management (PIM) を実装して、Azure AD と Azure リソースに Just-In-Time 特権アクセスを適用します。 また、アクセス権を持つユーザーを検出し、特権アクセスを確認することもできます。||![緑色のチェック マーク。](../media/green-check-mark.png)|
|特権アクセス管理を実装して、Office 365の特権管理タスクに対するきめ細かなアクセス制御を管理します。||![緑色のチェック マーク。](../media/green-check-mark.png)|
|Privileged Access Workstations (PAW) を構成して使用してサービスを管理します。 インターネットを参照し、管理アカウントに関連しないメールを確認する場合は、同じワークステーションを使用しないでください。|!![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png):::|

次の図は、これらの機能を示しています。
:::image type="content" source="../media/m365-security-bdm-illustrations-privileged-accounts.png" alt-text="特権アカウントを保護するための推奨される機能" lightbox="../media/m365-security-bdm-illustrations-privileged-accounts.png":::

追加の推奨事項:

- オンプレミスから同期されるアカウントにクラウド サービスの管理者ロールが割り当てられていないことを確認します。 これにより、攻撃者がクラウド サービスへの管理アクセスを得るためにオンプレミス アカウントを適用するのを防ぐことができます。
- サービス アカウントに管理者ロールが割り当てられていないことを確認します。 これらのアカウントは、多くの場合、有効期限が切れるパスワードで監視および設定されません。 まず、AADConnect および ADFS サービス アカウントが既定でグローバル管理者でないことを確認します。
- 管理者アカウントからライセンスを削除します。 特定の管理者アカウントにライセンスを割り当てる特定のユース ケースがない限り、これらのアカウントからライセンスを削除します。

## <a name="reduce-the-surface-of-attack"></a>攻撃の表面を減らす

次のフォーカス領域は、攻撃の表面を減らすことです。 これは、最小限の労力と、ユーザーとサービスへの影響を最小限に抑えて実現できます。 攻撃の領域を減らすことで、攻撃者は組織に対する攻撃を開始する方法が少なくなります。

次に、いくつかの例を示します:

- POP3、IMAP、SMTP プロトコルを無効にします。 ほとんどの最新の組織では、これらの古いプロトコルは使用されなくなりました。 これらを安全に無効にし、必要に応じて例外のみを許可できます。
- テナント内のグローバル管理者の数を減らして、必要最小限に抑えます。 これにより、すべてのクラウド アプリケーションに対する攻撃の領域が直接減少します。
- 環境で使用されなくなったサーバーとアプリケーションを廃止します。
- 使用されなくなったアカウントを無効にして削除するプロセスを実装します。

## <a name="protect-against-known-threats"></a>既知の脅威から保護する

既知の脅威には、マルウェア、侵害されたアカウント、フィッシングなどがあります。 これらの脅威に対する一部の保護は、ユーザーに直接影響を与えずに迅速に実装できますが、他のユーザーには、より多くの計画とユーザー トレーニングが必要です。

|推奨事項|E3|E5|
|---|---|---|
|**多要素認証を設定し、サインイン リスク ポリシーを含む推奨される条件付きアクセス ポリシーを使用します**。 Microsoft では、Office 365サービスやMicrosoft 365 サービスを含むすべてのクラウド アプリを保護するために連携する一連のポリシーを推奨し、テストしました。 [ID とデバイスアクセスの構成に関する説明を](./office-365-security/microsoft-365-policies-configurations.md)参照してください。||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**すべてのユーザーに多要素認証が必要** です。 推奨される条件付きアクセス ポリシーを実装するために必要なライセンスがない場合は、少なくともすべてのユーザーに多要素認証が必要です。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**メール内のマルウェアに対する保護のレベルを上げます**。 Office 365環境またはMicrosoft 365環境にはマルウェアに対する保護が含まれていますが、マルウェアでよく使用されるファイルの種類を含む添付ファイルをブロックすることで、この保護を強化できます。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**標的型フィッシング攻撃からメールを保護します**。 Office 365環境またはMicrosoft 365環境に対して 1 つ以上のカスタム ドメインを構成した場合は、対象となるフィッシング対策保護を構成できます。 Defender for Office 365の一部であるフィッシング対策保護は、悪意のある偽装ベースのフィッシング攻撃やその他のフィッシング攻撃から組織を保護するのに役立ちます。 カスタム ドメインを構成していない場合は、これを行う必要はありません。||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**電子メールでのランサムウェア攻撃から保護** します。 ランサムウェアは、ファイルを暗号化したり、コンピューター画面をロックしたりすることで、データへのアクセスを取り除きます。 その後、データへのアクセスを返すのと引き換えに、通常はビットコインのような形式の仮想通貨の形式で、"身代金" を求めることによって、被害者からお金を強要しようとします。 ランサムウェアに対して一般的に使用されるファイル拡張子をブロックする 1 つ以上のメール フロー ルールを作成したり、電子メールでこれらの添付ファイルを受信したユーザーに警告したりすることで、ランサムウェアから保護することができます。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**ビジネスを行わない国からの接続をブロック** します。 これらの国からの接続をブロックする Azure AD 条件付きアクセス ポリシーを作成し、テナントの周囲に geo ファイアウォールを効果的に作成します。||![緑色のチェック マーク。](../media/green-check-mark.png)|

次の図は、これらの機能を示しています。
:::image type="content" source="../media/m365-security-bdm-illustrations-known-threats.png" alt-text="既知の脅威から保護するための推奨される機能" lightbox="../media/m365-security-bdm-illustrations-known-threats.png":::

## <a name="protect-against-unknown-threats"></a>不明な脅威から保護する

特権アカウントに追加の保護を追加し、既知の攻撃から保護した後は、未知の脅威からの保護に注意を移します。 より断固として高度な敵対者は、革新的で新しい未知の方法を使用して組織を攻撃します。 数十億を超えるデバイス、アプリケーション、サービスを介して収集された Microsoft の膨大なテレメトリにより、Windows、Office 365、Azure でDefender for Office 365を実行して、Zero-Day攻撃を防ぎ、サンド ボックス環境を利用し、コンテンツへのアクセスを許可する前に有効性を確認することができます。

|推奨事項|E3|E5|
|---|---|---|
|**Microsoft Defender for Office 365を構成します**。<ul><li>安全な添付ファイル</li><li>安全なリンク</li><li>SPO、OneDrive、Teams 用の安全な添付ファイル機能</li><li>フィッシング対策ポリシーにおける、なりすまし保護</li></ul>||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**Microsoft Defender for Endpoint機能を構成します**。<ul><li>Windows Defender ウイルス対策</li><li>エクスプロイト保護</li><li>攻撃面の縮小</li><li>ハードウェアベースの分離</li><li>コントロールされたフォルダー アクセス</li></ul>||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**Microsoft Defender for Cloud Appsを使用して** SaaS アプリを検出し、動作分析と異常検出の使用を開始します。||![緑色のチェック マーク。](../media/green-check-mark.png)|

次の図は、これらの機能を示しています。
:::image type="content" source="../media/m365-security-bdm-illustrations-unknown-threats.png" alt-text="不明な脅威から保護するためのツールによって提供される機能の例" lightbox="../media/m365-security-bdm-illustrations-unknown-threats.png":::

追加の推奨事項:

- TLS を使用して電子メールなどのパートナー チャネル通信をセキュリティで保護します。
- Teamsフェデレーションは、通信相手のパートナーにのみ開きます。
- 送信者ドメイン、個々の送信者、または送信元 IP を許可リストに追加しないでください。これにより、スパムやマルウェアのチェックをバイパスできます。一般的な方法として、顧客は自分の承認済みドメインや、電子メール フローの問題が許可リストに報告されている可能性がある他の多くのドメインを追加します。 スパムと接続フィルターの一覧にドメインを追加しないでください。これはすべてのスパム チェックをバイパスする可能性があるためです。
- 送信スパム通知を有効にする - 内部ユーザーが外部からスパム メールを送信しているかどうかを報告するために、配布リストへの送信スパム通知をヘルプデスクまたは IT 管理者チームに内部的に有効にします。 これは、アカウントが侵害されたことを示すインジケーターである可能性があります。
- すべてのユーザーに対してリモート PowerShell を無効にします。リモート PowerShell は、主に管理者が管理目的またはプログラムによる API アクセスのためにサービスにアクセスするために使用されます。 管理者以外のユーザーがアクセスするビジネス要件がない限り、偵察を回避するには、このオプションを無効にすることをお勧めします。
- 管理者以外のすべてのユーザーに対するMicrosoft Azure管理ポータルへのアクセスをブロックします。 これを実現するには、管理者を除くすべてのユーザーをブロックする条件付きアクセス規則を作成します。

## <a name="assume-breach"></a>違反を想定する

Microsoft は脅威や攻撃を防ぐためにあらゆる手段を取りますが、常に "侵害を想定" の考え方に従って作業することをお勧めします。 攻撃者が環境に侵入できた場合でも、攻撃者が環境からデータや ID 情報を流出できないようにする必要があります。 このため、社会保障番号、クレジット カード番号、その他の個人情報、その他の組織レベルの機密情報などの機密データ漏洩に対する保護を有効にすることをお勧めします。

|推奨事項|E3|E5|
|---|---|---|
|**条件付きアクセスと関連するポリシーを確認して最適化し、ゼロ トラスト ネットワークの目標に合わせます**。 既知の脅威から保護するには、推奨される一連のポリシーを実装 [することが含まれます](./office-365-security/microsoft-365-policies-configurations.md)。 これらのポリシーの実装を確認して、ネットワークにアクセスしたハッカーからアプリとデータを保護していることを確認します。 Windows 10に推奨されるIntuneアプリ保護ポリシーでは、Windows Information Protection (WIP) が有効になります。 WIP は、電子メール、ソーシャル メディア、パブリック クラウドなどのアプリやサービスを通じて組織のデータが偶発的に漏えいするのを防ぎます。||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**外部メール転送を無効にします**。 ユーザーのメールボックスにアクセスするハッカーは、メールを自動的に転送するようにメールボックスを設定することで、メールを盗むことができます。 これは、ユーザーの認識がなくても発生する可能性があります。 メール フロー ルールを構成することで、これを防ぐことができます。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**匿名の外部予定表共有を無効にします**。 既定では、外部の匿名予定表共有が許可されます。 [予定表共有を無効にして](/exchange/sharing/sharing-policies/modify-a-sharing-policy) 、機密情報の漏えいの可能性を減らします。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**機密データのデータ損失防止ポリシーを構成します**。 Microsoft Purview データ損失防止ポリシーを作成して、クレジット カード番号、社会保障番号、銀行口座番号などの機密データを検出して保護します。 Microsoft 365には、データ損失防止ポリシーで使用できる定義済みの機密情報の種類が多数含まれています。 また、環境に合わせてカスタムの機密データ用に独自の機密情報の種類を作成することもできます。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**データ分類と情報保護ポリシーを実装する**。 機密ラベルを実装し、これらを使用して機密データを分類して保護を適用します。 これらのラベルは、データ損失防止ポリシーでも使用できます。 Azure Information Protection ラベルを使用している場合は、他の管理センターで新しいラベルを作成しないことをお勧めします。||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**Defender for Cloud アプリを使用して、サード パーティ製のアプリとサービスのデータを保護します**。 Defender for Cloud アプリ ポリシーを構成して、Salesforce、Box、Dropboxなど、サードパーティのクラウド アプリ全体で機密情報を保護します。 Defender for Cloud Apps ポリシーで作成した機密情報の種類と秘密度ラベルを使用し、SaaS アプリに適用できます。 <p> Microsoft Defender for Cloud Appsでは、さまざまな自動化されたプロセスを適用できます。 ポリシーは、継続的なコンプライアンス スキャン、法的電子情報開示タスク、機密コンテンツの DLP をパブリックに共有するように設定できます。 Defender for Cloud アプリは、20 を超えるメタデータ フィルター (アクセス レベル、ファイルの種類など) に基づいて、任意のファイルの種類を監視できます。||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview)を使用して、ユーザーがWindows デバイスに機密情報を格納しているかどうかを識別します**。||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**[AIP スキャナー](/azure/information-protection/deploy-aip-scanner)を使用して、サーバーとファイル共有間で情報を識別して分類** します。 AIP レポート ツールを使用して結果を表示し、適切なアクションを実行します。||![緑色のチェック マーク。](../media/green-check-mark.png)|

次の図は、これらの機能を示しています。
:::image type="content" source="../media/m365-security-bdm-illustrations-assume-breach.png" alt-text="不明な脅威から保護するために推奨される機能" lightbox="../media/m365-security-bdm-illustrations-assume-breach.png":::

## <a name="continuous-monitoring-and-auditing"></a>継続的な監視と監査

最後に、Microsoft 365環境とWindowsおよびデバイスの継続的な監視と監査は、侵入をすばやく検出して修復できるようにするために重要です。 Secure Score、Microsoft 365 Defender ポータル、Microsoft Intelligent Graphの高度な分析などのツールは、テナントに貴重な情報を提供し、膨大な量の脅威インテリジェンスとセキュリティ データをリンクして、比類のない脅威の保護と検出を提供します。

|推奨事項|E3|E5|
|---|---|---|
|**監査ログ** がオンになっていることを確認します。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**セキュリティスコアを毎週確認** する - セキュリティスコアは、会社のセキュリティ状態にアクセスし、セキュリティスコアの推奨事項に基づいてアクションを実行するための中心的な場所です。 毎週このチェックを実行することをお勧めします。|![緑色のチェック マーク。](../media/green-check-mark.png)|![緑色のチェック マーク。](../media/green-check-mark.png)|
|**Microsoft Defender for Office 365 ツールを** 使用します。 <ul><li>脅威の調査と対応の機能</li><li>自動調査および対応</li></ul>||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**Microsoft Defender for Endpoint** を使用します。 <ul><li>[エンドポイントでの検出と対応](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)</li><li>自動調査と修復のセキュリティスコア</li><li>[高度な追求](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)</li></ul>||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**Microsoft Defender for Cloud Apps** を使用してクラウド アプリ間の異常な動作を検出し、ランサムウェア、侵害されたユーザー、または不正なアプリケーションを特定し、リスクの高い使用状況を分析し、自動的に修復してリスクを組織に限定します。||:::image type="content" source="../media/green-check-mark.png" alt-text="緑色のチェック マークの例" lightbox="../media/green-check-mark.png":::|
|**Microsoft Sentinel** または現在の SIEM ツールを使用して、環境全体の脅威を監視します。||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)をデプロイ** して、オンプレミスの Active Directory環境を対象とした脅威を監視し、保護します。||![緑色のチェック マーク。](../media/green-check-mark.png)|
|**Microsoft Defender for Cloud** を使用して、ハイブリッドワークロードとクラウド ワークロード全体の脅威を監視します。 Microsoft Defender for Cloudには、無料レベルの機能と、リソース時間またはトランザクションに基づいて支払われる標準レベルの機能が含まれます。

次の図は、これらの機能を示しています。

:::image type="content" source="../media/m365-security-bdm-illustrations-monitoring-auditing.png" alt-text="継続的な監視と監査に推奨される機能" lightbox="../media/m365-security-bdm-illustrations-monitoring-auditing.png":::

最も推奨される監視アクション:

- **Microsoft Secure Score を毎週確認** する - セキュリティ スコアは、テナントのセキュリティ状態にアクセスし、最高の推奨事項に基づいてアクションを実行するための中心的な場所です。 毎週このチェックを実行することをお勧めします。 セキュリティスコアには、Azure AD、Intune、Defender for Cloud Apps、Microsoft Defender for Endpoint、Office 365に関する推奨事項が含まれます。
- **危険なログインを毎週確認する** - Azure AD 管理センターを使用して、危険なサインインを毎週確認します。 推奨される ID およびデバイス アクセス 規則セットには、危険なサインインにパスワード変更を適用するポリシーが含まれています。
- **マルウェアとフィッシング詐欺の上位ユーザーを毎週確認** する - 脅威エクスプローラー Microsoft Defender for Office 365使用して、マルウェアとフィッシングの対象となる上位ユーザーを確認し、これらのユーザーが影響を受ける理由の根本原因を確認します。
