---
title: Microsoft マネージド デスクトップのテクノロジ
description: この記事では、Microsoft Managed Desktopで使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: d7a7b6889451d83aaa6c2b53c1dce6ed035f9916
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64945629"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft マネージド デスクトップのテクノロジ

この記事では、Microsoft Managed Desktopで使用されるテクノロジとアプリの一覧を示します。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise ライセンスはすべてのMicrosoft Managed Desktop ユーザーに必要です。 サービスのライセンス要件の詳細については、「[Microsoft Managed Desktopの前提条件」を参照してください](../get-ready/prerequisites.md)。

この記事では、必要なEnterprise ライセンスに含まれるコンポーネントと、サービスがMicrosoft Managed Desktop デバイスで各コンポーネントを使用する方法について説明します。 各領域の具体的な役割と責任については、Microsoft Managed Desktopドキュメント全体で詳しく説明されています。

## <a name="office-365-e3-or-e5"></a>Office 365 E3または E5

| 製品 | 情報 |
| ----- | ----- |
| Microsoft 365 Apps for enterprise (64 ビット) | 次のOfficeアプリケーションがデバイスに付属します。<br><ul><li>Word</li><li>Excel</li><li>PowerPoint</li><li>Outlook</li><li>発行者</li><li>Access</li><li>Skype for Business</li><li>OneNote</li></ul><br>Microsoft Projectと Microsoft Visioの 64 ビットフル バージョンは含まれません。 ただし、これらのアプリケーションのインストールは、Enterprise インストールのMicrosoft 365 Appsに依存するため、既定のMicrosoft Intune展開を作成Microsoft Managed Desktop、これらのアプリケーションをライセンスユーザーに展開するために使用できるセキュリティ グループが作成されます。 詳細については、「[Microsoft Managed Desktop デバイスにMicrosoft Projectまたは Microsoft Visioをインストールする」を参照してください](../get-started/project-visio.md)。 |
| OneDrive | Azure Active Directoryシングル サインオンは、ユーザーが最初にOneDriveにサインインしたときに有効になります。<br><br>デスクトップ、ドキュメント、およびピクチャフォルダーの既知のフォルダー リダイレクトが含まれています。 これらのフォルダーは、Microsoft Managed Desktopによって有効および構成されます。 |
| ストア アプリ | Microsoft SwayとPower BIはデバイスに付属していません。 これらのアプリは、Microsoft Storeからダウンロードできます。 |
| Win32 アプリケーション | Teamsはデバイスに付属していませんが、パッケージ化され、Microsoft Managed Desktop デバイス用に Microsoft によって提供されます。 Azure Information Protection クライアントはデバイスに付属していませんが、デプロイ用にパッケージ化することもできます。 |
| Web アプリケーション | 次の Web アプリケーションはデバイスに付属していません。 <ul><li>Yammer</li><li>ブラウザーでのOffice</li><li>Delve</li><li>Flow</li><li>StaffHub</li><li>Power Apps</li><li>Planner</li></ul> <br>ユーザーは、ブラウザーを使用してこれらのアプリケーションの Web バージョンにアクセスできます。 |

## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointを使用して E5 または E3 をWindows 10 Enterpriseする

IT 管理者は、次の設定を構成することをお勧めします。

> [!NOTE]
> これらの設定は、Microsoft Managed Desktopの一部として含まれるか、管理されません。

| 製品 | 情報 |
| ----- | ----- |
| Windows Hello for Business | Microsoft Managed Desktop デバイスの強力な 2 要素認証でパスワードを置き換えるWindows Hello for Businessを実装する必要があります。 詳細については、「[Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification)」を参照してください。 |
| アプリケーション仮想化 | Intune Win32 アプリ管理クライアントを使用して、アプリケーション仮想化 (App-V) パッケージをデプロイできます。 詳細については、「 [アプリケーションの仮想化」を](/windows/application-management/app-v/appv-technical-reference)参照してください。 |
| Microsoft Purview データ損失防止 | データ損失防止を実装して、機密性が高いと判断したアイテムに対して実行されたアクションを監視し、それらのアイテムの意図しない共有を防ぐのに役立つ必要があります。 詳細については、「 [データ損失防止](../../compliance/endpoint-dlp-learn-about.md)」を参照してください。 |

Microsoft Managed Desktopの一部として含まれる機能と管理されている機能:

| 製品 | 情報 |
| ----- | ----- |
| BitLocker ドライブ暗号化 | BitLocker ドライブ暗号化は、すべてのシステム ドライブを暗号化するために使用されます。 詳細については、「 [BitLocker ドライブの暗号化](/windows/security/information-protection/bitlocker/bitlocker-overview)」を参照してください。 |
| Windows Defender System Guard | 起動時にシステムの整合性を保護し、システムの整合性が本当に維持されていることを検証します。 詳細については、「[Windows Defender System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)」を参照してください。 |
| Windows Defender Credential Guard | Windows Defender Credential Guard では、仮想化ベースのセキュリティを使用してシークレットを分離し、特権システム ソフトウェアのみがシークレットにアクセスできるようにします。 詳細については、「[Windows Defender System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)」を参照してください。 |
| Microsoft Defender for Endpoint - エンドポイントの検出と応答 | Microsoft Managed Desktop セキュリティ操作はアラートに応答し、エンドポイントの検出と応答を使用して脅威を修復するアクションを実行します。 詳細については、「[Microsoft Defender for Endpoint - エンドポイントの検出と応答」を](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)参照してください。 |
| Microsoft Defender for Endpoint - 脅威エキスパート | Microsoft Managed Desktopは、標的型攻撃通知を通じて脅威エキスパートの分析情報とデータと統合されます。 このサービスを有効にする前に、追加の同意を提供する必要があります。 詳細については、「[Microsoft Defender for Endpoint - 脅威エキスパート」を](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)参照してください。 |
| Microsoft Defender for Endpoint - 脅威と脆弱性の管理 | Microsoft Managed Desktop サービス プランで将来使用するために必要です。 詳細については、「[Microsoft Defender for Endpoint - 脅威と脆弱性の管理」を](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)参照してください。 |
| Microsoft Defender for Endpoint - 攻撃面の縮小 | 攻撃者によって頻繁に悪用される危険なソフトウェア動作をターゲットにします。 詳細については、「[Microsoft Defender for Endpoint - 攻撃面の縮小」を](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)参照してください。 |
| Microsoft Defender for Endpoint - Exploit Protection | 悪用を使用してデバイスに感染するマルウェアから保護し、オペレーティング システムのプロセスとアプリに悪用軽減手法を自動的に適用することで拡散します。 詳細については、「[Microsoft Defender for Endpoint - Exploit Protection](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)」を参照してください。 |
| Microsoft Defender for Endpoint - Network Protection | Microsoft Defender SmartScreenの範囲を拡張して、低評価ソースへの接続を試みるすべての送信 HTTP および HTTPS トラフィックをブロックします。 詳細については、「[Microsoft Defender for Endpoint - Network Protection](/windows/security/threat-protection/microsoft-defender-atp/network-protection)」を参照してください。 |
| Microsoft Defender 改ざん防止 | Windows改ざん防止は、ウイルス対策などのセキュリティ設定が変更されないようにするために使用されます。 詳細については、「 [Microsoft Defender 改ざん防止](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)」を参照してください。 |
| Microsoft Defender ウイルス対策動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護 | 常にオンにして、マルウェアとして検出されない可能性があるファイルとプロセスの脅威をスキャンします。 詳細については、「[Microsoft Defender ウイルス対策動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護](../../security/defender-endpoint/microsoft-defender-antivirus-in-windows-10.md)」を参照してください。 |
| クラウド配信保護Microsoft Defender ウイルス対策 | 新しい脅威や新しい脅威に対する動的なほぼ瞬時の自動保護を提供します。 詳細については、「[クラウド配信保護Microsoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)」を参照してください。 |
| Microsoft Defender for Endpoint - "一目でブロック" | Windowsが疑わしいファイルや不明なファイルを検出したときに、新しいマルウェアの検出とブロックを提供します。 詳細については、「[Microsoft Defender for Endpoint - 一目でブロックする」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。 |
| Microsoft Defender ウイルス対策望ましくない可能性があるアプリケーション | コンピューターの実行速度が低下する可能性のあるアプリをブロックしたり、予期しない広告を表示したり、最悪の場合は、予期しないソフトウェアや望ましくない可能性がある他のソフトウェアをインストールしたりするために使用されます。 詳細については、「[不要と思われるアプリケーションのMicrosoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)」を参照してください。 |
| 高度なセキュリティを備えたファイアウォールのWindows Defender | デバイスのホスト ベースの双方向ネットワーク トラフィック フィルター処理Windows Defenderファイアウォールは、ローカル デバイスに出入りする未承認のネットワーク トラフィックをブロックします。 詳細については、「[セキュリティが強化されたファイアウォールのWindows Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)」を参照してください。 |
| ユーザー アカウント制御 | タスクまたはアクションで管理者アカウントの種類のアクセスが必要な場合、ユーザー アカウント制御は Secure Desktop に切り替わります。 Microsoft Managed Desktopユーザーには、登録時に Standard ユーザー アクセスが割り当てられます。 詳細については、「 [ユーザー アカウント制御」を](/windows/security/identity-protection/user-account-control/how-user-account-control-works)参照してください。 |

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

| 製品 | 情報 |
| ----- | ----- |
| Enterprise Mobility + Security E3<br><br>Azure Active Directory Premium P2 | Enterprise Mobility + Security E3のすべての機能を使用して、MDM デバイスを管理できます。<br><br>Microsoft Managed Desktopでは、オプションの機能としてAzure Active Directory Premium P2を使用できます。 |
| Microsoft Defender for Cloud Apps | このオプション機能は、Microsoft Managed Desktopで使用できます。
| Azure Information Protection P2  | このオプション機能は、Microsoft Managed Desktopで使用できます。
