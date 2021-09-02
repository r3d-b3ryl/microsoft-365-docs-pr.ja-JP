---
title: Microsoft マネージド デスクトップのテクノロジ
description: この記事では、アプリで使用されるテクノロジとアプリMicrosoft マネージド デスクトップ。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: dd8293f05a5b88bbd17a3b6760c9a535737fd439
ms.sourcegitcommit: ef9cd046c47b340686a4f7bb123ea3b0a269769a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2021
ms.locfileid: "58863883"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft マネージド デスクトップのテクノロジ

この記事では、アプリで使用されるテクノロジとアプリMicrosoft マネージド デスクトップ。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterpriseユーザーには、ライセンスのMicrosoft マネージド デスクトップがあります。 サービスのライセンス要件の詳細については、「サービスの前提条件」[を参照Microsoft マネージド デスクトップ。](../get-ready/prerequisites.md)

この記事では、必要な Enterprise ライセンスに含まれるコンポーネントの概要と、サービスが各コンポーネントをデバイスでどのように使用Microsoft マネージド デスクトップします。 各領域の特定の役割と責任については、各ドキュメントMicrosoft マネージド デスクトップされています。 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 E5

| 製品 |情報 |
--- |--- 
Microsoft 365 Apps for enterprise (64 ビット) | これらのOfficeアプリケーションは、Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote に同梱されます。<br><br>64 ビット版のフル バージョンの Microsoft Project Microsoft Visioは含まれていません。 ただし、これらのアプリケーションのインストールは Microsoft 365 Apps for enterprise インストールに依存しますので、Microsoft マネージド デスクトップ は既定の Microsoft Intune 展開とセキュリティ グループを作成し、これらのアプリケーションをライセンスユーザーに展開するために使用できます。 詳細については、「デバイスにインストール[するMicrosoft Projectまたは Microsoft Visio」をMicrosoft マネージド デスクトップしてください](../get-started/project-visio.md)。
OneDrive |Azure Active Directoryシングル サインオンは、ユーザーが最初にユーザーにサインインするときに有効OneDrive。<br><br>"Desktop"、"Document"、"Pictures" フォルダーの既知のフォルダー リダイレクトが含まれています。を有効にし、Microsoft マネージド デスクトップ。
ストア アプリ | Microsoft Sway と Power BIデバイスには同梱されません。 これらのアプリは、アプリからダウンロードMicrosoft Store。
Win32 アプリケーション | Teamsはデバイスに同梱されませんが、Microsoft によってパッケージ化され、デバイスにMicrosoft マネージド デスクトップされます。 Azure Information Protection Client はデバイスに同梱されませんが、展開用にパッケージ化できます。
Web アプリケーション | Yammer、Office、Delve、Flow、StaffHub、Power Apps、Planner はデバイスに同梱されません。 ユーザーは、ブラウザーを使用してこれらのアプリケーションの Web バージョンにアクセスできます。

## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterpriseエンドポイント用 Microsoft Defender を使用した E5 または E3

IT 管理者が次の設定を構成することをお勧めします。 これらの設定は、アプリの一部として含めMicrosoft マネージド デスクトップ。

製品  |情報
--- | ---
Windows Hello for Business | パスワードをデバイスWindows Hello強力な 2 要素認証に置き換えるには、Microsoft マネージド デスクトップする必要があります。 詳細については、「ビジネス向[けWindows Hello」を参照してください](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。
アプリケーションの仮想化 | Intune Win32 アプリ管理クライアントを使用して、アプリケーション仮想化 (App-V) パッケージを展開できます。 詳細については [、「Application Virtualization 」を参照してください](/windows/application-management/app-v/appv-technical-reference)。
Microsoft 365データ損失防止 | 機密と判断したMicrosoft 365に対して実行されているアクションを監視し、それらのアイテムが意図せずに共有されるのを防ぐために、データ損失防止を実装する必要があります。 詳細については、「データ損失[防止Microsoft 365を参照してください](../../compliance/endpoint-dlp-learn-about.md)。

次に示す機能は、次の機能の一Microsoft マネージド デスクトップ。

製品 |情報
--- |---
BitLocker ドライブの暗号化 | BitLocker ドライブの暗号化は、すべてのシステム ドライブを暗号化するために使用されます。 詳細については [、「BitLocker ドライブの暗号化」を参照してください](/windows/security/information-protection/bitlocker/bitlocker-overview)。
Windows DefenderSystem Guard | 起動時にシステムの整合性を保護し、システムの整合性が本当に維持されたと検証します。 詳細については、「System [Guard のWindows Defenderを参照してください](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)。
Windows Defender Credential Guard | Windows DefenderCredential Guard は仮想化ベースのセキュリティを使用してシークレットを分離し、特権のあるシステム ソフトウェアだけがアクセスできます。 詳細については、「System [Guard のWindows Defenderを参照してください](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)。
エンドポイント向け Microsoft Defender - エンドポイントの検出と応答 | Microsoft マネージド デスクトップセキュリティ操作は、アラートに応答し、エンドポイント検出と応答を使用して脅威を修復するアクションを実行します。 詳細については [、「Microsoft Defender for Endpoint - Endpoint Detection and Response 」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)。
Microsoft Defender for Endpoint - Threat Experts | Microsoft マネージド デスクトップ攻撃通知を通じて脅威エキスパートの分析情報やデータと統合できます。 このサービスを有効にする前に、追加の同意を提供する必要があります。 詳細については [、「Microsoft Defender for Endpoint - Threat Experts」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)。
エンドポイント向け Microsoft Defender - 脅威と脆弱性の管理 | サービス プランの将来の使用Microsoft マネージド デスクトップ必要です。 詳細については [、「Microsoft Defender for Endpoint - Threat and Vulnerability Management」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。
エンドポイント向け Microsoft Defender - 攻撃表面の縮小 | 攻撃表面の縮小は、攻撃者によって悪用されるリスクの高いソフトウェアの動作をターゲットにしています。 詳細については [、「Microsoft Defender for Endpoint - Attack Surface Reduction 」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。
Microsoft Defender for Endpoint - Exploit Protection | エクスプロイトを使用してデバイスに感染し、オペレーティング システム プロセスとアプリの両方に悪用の軽減手法を自動的に適用することで、マルウェアから保護します。 詳細については [、「Microsoft Defender for Endpoint - Exploit Protection」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)。
Microsoft Defender for Endpoint - ネットワーク保護 | ネットワーク保護は、低Microsoft Defender SmartScreenに接続しようとするすべての送信 HTTP および HTTPS トラフィックをブロックするように、ネットワーク保護の範囲を拡張します。 詳細については [、「Microsoft Defender for Endpoint - Network Protection」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/network-protection)。
Microsoft Defender タンパープロテクション | Windowsタンパープロテクションは、ウイルス対策保護などのセキュリティ設定が変更されるのを防ぐために使用されます。 詳細については [、「Microsoft Defender タンパー プロテクション」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)。
Microsoft Defender ウイルス対策動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護 | 常にファイルをスキャンし、マルウェアとして検出されない可能性のある脅威を処理します。 詳細については、「Microsoft Defender ウイルス対策、ヒューリスティック、リアルタイムのウイルス対策保護」[を参照してください](../../security/defender-endpoint/microsoft-defender-antivirus-in-windows-10.md)。
Microsoft Defender ウイルス対策クラウド配信の保護 | 新しい脅威や新しい脅威に対する動的なほぼ瞬時の自動保護を提供します。 詳細については、「クラウド配信[Microsoft Defender ウイルス対策」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)。
Microsoft Defender "一目でブロックする" | 疑わしいファイルまたは不明なファイルを検出Windows新しいマルウェアの検出とブロックを提供します。 詳細については [、「Microsoft Defender Block at first sight」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。
Microsoft Defender ウイルス対策望ましくない可能性のあるアプリケーション | 望ましくない可能性のあるアプリケーションは、コンピューターの動作が遅くなる、予期しない広告を表示する、または最悪の場合は予期しない、または望ましくない可能性のある他のソフトウェアをインストールするアプリをブロックするために使用されます。 詳細については、「潜在的に望[ましくないMicrosoft Defender ウイルス対策アプリケーション」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)。
Windows Defender高度なセキュリティを備えファイアウォール | デバイスのホスト ベースの、2 方向ネットワーク トラフィック フィルタリング、Windows Defender ファイアウォールは、ローカル デバイスに対して、またはローカル デバイスから流れ出る未承認のネットワーク トラフィックをブロックします。 詳細については、「Advanced [Security Windows Defenderファイアウォール」を参照してください](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。
ユーザー アカウント制御 | タスクまたはアクションで管理者アカウントタイプのアクセスが必要な場合、ユーザー アカウント制御は Secure Desktop に切り替わります。 Microsoft マネージド デスクトップユーザーには、登録時に標準ユーザー アクセス権が割り当てられます。 詳細については、「User [Account Control」を参照してください](/windows/security/identity-protection/user-account-control/how-user-account-control-works)。


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + SecurityE5

製品 |情報
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 | MDM デバイスの管理には、Enterprise Mobility + Security E3機能を使用できます。 この機能は、Azure Active Directory Premium P2オプション機能として使用Microsoft マネージド デスクトップ。
Microsoft Cloud App Security | このオプション機能は、このオプション機能とMicrosoft マネージド デスクトップ。
Azure Information Protection P2  | このオプション機能は、このオプション機能とMicrosoft マネージド デスクトップ。
