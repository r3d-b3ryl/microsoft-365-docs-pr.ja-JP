---
title: Microsoft マネージド デスクトップのテクノロジ
description: この記事では、Microsoft Managed Desktop で使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: ec99a478cb085e3e7692d2e489851d4abf4c2bb4
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034439"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft マネージド デスクトップのテクノロジ

この記事では、Microsoft Managed Desktop で使用されるテクノロジとアプリの一覧を示します。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise Microsoft Managed Desktop ユーザーには、ライセンスの取得が必要です。 サービスのライセンス要件の詳細については [、「Microsoft Managed Desktop の前提条件」を参照してください](../get-ready/prerequisites.md)。

この記事では、必要な Enterprise ライセンスに含まれるコンポーネントの概要と、Microsoft Managed Desktop デバイスでサービスが各コンポーネントを使用する方法について説明します。 各領域の特定の役割と責任については、Microsoft Managed Desktop のドキュメントを通じて詳しく説明します。 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 E5

| 製品 |情報 |
--- |--- 
Microsoft 365 Apps for enterprise (64 ビット) | これらのOfficeアプリケーションは、Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote に同梱されます。<br><br>64 ビット版のフル バージョンの Microsoft Project Microsoft Visioは含まれていません。 ただし、これらのアプリケーションのインストールは Microsoft 365 Apps for enterprise インストールに依存しますので、Microsoft Managed Desktop は既定の Microsoft Intune 展開とセキュリティ グループを作成し、ライセンスを持つユーザーにこれらのアプリケーションを展開するために使用できます。 詳細については[、「Install Microsoft Project」または「Microsoft Visio デスクトップ デバイスにインストールする」を参照してください](../get-started/project-visio.md)。
OneDrive |Azure Active Directoryユーザーが最初にサインインするときに、シングル サインオンが有効OneDrive。<br><br>"Desktop"、"Document"、"Pictures" フォルダーの既知のフォルダー リダイレクトが含まれています。Microsoft Managed Desktop によって有効および構成されます。
ストア アプリ | Microsoft Sway と Power BIデバイスには同梱されません。 これらのアプリは、アプリからダウンロードMicrosoft Store。
Win32 アプリケーション | Teamsは、デバイスには同梱されませんが、Microsoft によって Microsoft 管理デスクトップ デバイス用にパッケージ化され、提供されます。 Azure Information Protection Client はデバイスに同梱されませんが、展開用にパッケージ化できます。
Web アプリケーション | Yammer、Office、Delve、Flow、StaffHub、Power Apps、Planner はデバイスに同梱されません。 ユーザーは、ブラウザーを使用してこれらのアプリケーションの Web バージョンにアクセスできます。

## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterpriseエンドポイント用 Microsoft Defender を使用して E5 または E3 を使用する

IT 管理者が次の設定を構成することをお勧めします。 これらの設定は、Microsoft Managed Desktop の一部として含まれるか、管理される必要はありません。

製品  |情報
--- | ---
Windows Hello for Business | Microsoft Managed Desktop デバイスWindows Hello強力な 2 要素認証にパスワードを置き換える場合は、ビジネス向けパスワードを実装する必要があります。 詳細については、「ビジネス向[けWindows Hello」を参照してください](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。
アプリケーションの仮想化 | Intune Win32 アプリ管理クライアントを使用して、アプリケーション仮想化 (App-V) パッケージを展開できます。 詳細については [、「Application Virtualization 」を参照してください](/windows/application-management/app-v/appv-technical-reference)。
Microsoft 365データ損失防止 | 機密と判断したMicrosoft 365に対して実行されているアクションを監視し、それらのアイテムが意図せずに共有されるのを防ぐために、データ損失防止を実装する必要があります。 詳細については、「データ損失[防止Microsoft 365を参照してください](../../compliance/endpoint-dlp-learn-about.md)。

Microsoft Managed Desktop の一部として含まれる機能と管理機能:

製品 |情報
--- |---
BitLocker ドライブの暗号化 | BitLocker ドライブの暗号化は、すべてのシステム ドライブを暗号化するために使用されます。 詳細については [、「BitLocker ドライブの暗号化」を参照してください](/windows/security/information-protection/bitlocker/bitlocker-overview)。
Windows Defender System Guard | 起動時にシステムの整合性を保護し、システムの整合性が本当に維持されたと検証します。 詳細については、「System [Guard のWindows Defenderを参照してください](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)。
Windows Defender Credential Guard | Windows Defender Credential Guard は仮想化ベースのセキュリティを使用してシークレットを分離し、特権のあるシステム ソフトウェアだけがアクセスできます。 詳細については、「System [Guard のWindows Defenderを参照してください](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)。
エンドポイント向け Microsoft Defender - エンドポイントの検出と応答 | Microsoft Managed Desktop Security Operations はアラートに応答し、エンドポイント検出と応答を使用して脅威を修復するアクションを実行します。 詳細については [、「Microsoft Defender for Endpoint - Endpoint Detection and Response 」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)。
Microsoft Defender for Endpoint - Threat Experts | Microsoft Managed Desktop は、標的型攻撃通知を通じて脅威エキスパートの分析情報とデータを統合します。 このサービスを有効にする前に、追加の同意を提供する必要があります。 詳細については [、「Microsoft Defender for Endpoint - Threat Experts」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)。
エンドポイント向け Microsoft Defender - 脅威と脆弱性の管理 | Microsoft Managed Desktop サービス プランでの将来の使用に必要です。 詳細については [、「Microsoft Defender for Endpoint - Threat and Vulnerability Management」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。
エンドポイント向け Microsoft Defender - 攻撃表面の縮小 | 攻撃表面の縮小は、攻撃者によって悪用されるリスクの高いソフトウェアの動作をターゲットにしています。 詳細については [、「Microsoft Defender for Endpoint - Attack Surface Reduction 」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。
Microsoft Defender for Endpoint - Exploit Protection | エクスプロイトを使用してデバイスに感染し、オペレーティング システム プロセスとアプリの両方に悪用の軽減手法を自動的に適用することで、マルウェアから保護します。 詳細については [、「Microsoft Defender for Endpoint - Exploit Protection」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)。
Microsoft Defender for Endpoint - ネットワーク保護 | ネットワーク保護は、低Microsoft Defender SmartScreenに接続しようとするすべての送信 HTTP および HTTPS トラフィックをブロックするように、ネットワーク保護の範囲を拡張します。 詳細については [、「Microsoft Defender for Endpoint - Network Protection」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/network-protection)。
Microsoft Defender タンパープロテクション | Windowsタンパープロテクションは、ウイルス対策保護などのセキュリティ設定が変更されるのを防ぐために使用されます。 詳細については [、「Microsoft Defender タンパー プロテクション」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)。
Microsoft Defender ウイルス対策ベース、ヒューリスティック、リアルタイムのウイルス対策保護 | 常にファイルをスキャンし、マルウェアとして検出されない可能性のある脅威を処理します。 詳細については、「Microsoft Defender ウイルス対策、ヒューリスティック、リアルタイムのウイルス対策保護」[を参照してください](../../security/defender-endpoint/microsoft-defender-antivirus-in-windows-10.md)。
Microsoft Defender ウイルス対策提供の保護 | 新しい脅威や新しい脅威に対する動的なほぼ瞬時の自動保護を提供します。 詳細については、「クラウド配信[Microsoft Defender ウイルス対策」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)。
エンドポイント用 Microsoft Defender - "一目でブロック" | 疑わしいファイルまたは不明なファイルを検出Windows新しいマルウェアの検出とブロックを提供します。 詳細については [、「Microsoft Defender for Endpoint - Block at first sight」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。
Microsoft Defender ウイルス対策望ましくない可能性のあるアプリケーション | 望ましくない可能性のあるアプリケーションは、コンピューターの動作が遅くなる、予期しない広告を表示する、または最悪の場合は予期しない、または望ましくない可能性のある他のソフトウェアをインストールするアプリをブロックするために使用されます。 詳細については、「潜在的に望[ましくないMicrosoft Defender ウイルス対策アプリケーション」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)。
Windows Defenderセキュリティを使用したファイアウォール | デバイスのホスト ベースの、2 方向ネットワーク トラフィック フィルタリング、Windows Defender ファイアウォールは、ローカル デバイスに対して、またはローカル デバイスから流れ出る未承認のネットワーク トラフィックをブロックします。 詳細については、「Advanced [Security Windows Defenderファイアウォール」を参照してください](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。
ユーザー アカウント制御 | タスクまたはアクションで管理者アカウントタイプのアクセスが必要な場合、ユーザー アカウント制御は Secure Desktop に切り替わります。 Microsoft Managed Desktop ユーザーには、登録時に Standard ユーザー アクセスが割り当てられます。 詳細については、「User [Account Control」を参照してください](/windows/security/identity-protection/user-account-control/how-user-account-control-works)。


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

製品 |情報
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 | MDM デバイスの管理には、Enterprise Mobility + Security E3機能を使用できます。 Microsoft Managed Desktop Azure Active Directory Premium P2オプション機能として使用できます。
Microsoft Defender for Cloud Apps | このオプション機能は、Microsoft Managed Desktop と一緒に使用できます。
Azure Information Protection P2  | このオプション機能は、Microsoft Managed Desktop と一緒に使用できます。
