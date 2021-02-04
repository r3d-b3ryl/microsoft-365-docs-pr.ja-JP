---
title: Microsoft マネージド デスクトップのテクノロジ
description: この記事では、Microsoft マネージド デスクトップで使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 4932a40455c8ed4d8fdfc0dfae99c8001e582ff4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094869"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft マネージド デスクトップのテクノロジ

この記事では、Microsoft マネージド デスクトップで使用されるテクノロジとアプリの一覧を示します。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise ライセンスは、すべての Microsoft マネージド デスクトップ ユーザーに必要です。 サービスのライセンス要件の詳細については、「Microsoft マネージド デスクトップの前提条件」 [を参照してください](../get-ready/prerequisites.md)。

この記事では、必要なエンタープライズ ライセンスに含まれるコンポーネントの概要と、サービスが Microsoft マネージド デスクトップ デバイスで各コンポーネントを使用する方法について説明します。 各領域の特定の役割と責任については、Microsoft マネージド デスクトップのドキュメント全体で詳しく説明します。 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 または E5
 |
 --- | ---
Microsoft 365 Apps for enterprise (64 ビット) | これらのOffice、Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote のデバイスに同梱されます。<br><br>64 ビット版の Microsoft Project および Microsoft Visio は含まれていません。 ただし、これらのアプリケーションのインストールは Microsoft 365 Apps for enterprise インストールに依存します。このため、Microsoft マネージド デスクトップでは、ライセンスを取得したユーザーにこれらのアプリケーションを展開するために使用できる既定の Microsoft Intune 展開とセキュリティ グループが作成されています。 詳細については、「Microsoft マネージ デスクトップ デバイスへの [Microsoft Project または Microsoft Visio のインストール」を参照してください](../get-started/project-visio.md)。
OneDrive |Azure Active Directory シングル サインオンは、ユーザーが初めて OneDrive にサインインするときに有効になります。<br><br>"Desktop"、"Document"、および "Pictures" フォルダーの既知のフォルダー リダイレクトが含まれます。有効にし、Microsoft マネージド デスクトップによって構成されます。
ストア アプリ |    Microsoft Sway と Power BI はデバイスに同梱されません。 これらのアプリは、Microsoft Store からダウンロードできます。
Win32 アプリケーション |    Teams はデバイスに同梱されませんが、Microsoft によって Microsoft マネージド デスクトップ デバイス用にパッケージ化され、提供されます。 Azure Information Protection クライアントはデバイスに同梱されませんが、展開用にパッケージ化することができます。
Web アプリケーション |  Yammer、Office Delve、Flow、StaffHub、PowerApps、Planner はデバイスに同梱されません。 ユーザーはブラウザーを使用してこれらのアプリケーションの Web バージョンにアクセスできます。



## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 または E3 と Microsoft Defender for Endpoint
推奨
 |
 --- | ---
[Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) | お客様は、Windows Hello for Business を実装して、パスワードを Microsoft マネージド デスクトップ デバイスで使用される強力な 2 要素認証に置き換える方法をお勧めします。
[Application Virtualization](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference) | お客様は、Intune Win32 アプリ管理クライアントを使用して Application Virtualization (App-V) パッケージを展開できます。
[Microsoft 365 データ損失防止](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about) | お客様は、Microsoft 365 データ損失防止 (DLP) を実装して、機密性が高いと判断されたアイテムに対して実行されているアクションを監視し、それらのアイテムが意図せずに共有されるのを防ぐことをお勧めします。   

サービスに含まれていて管理されている
 |
 --- | ---
[BitLocker ドライブの暗号化](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) | BitLocker ドライブ暗号化は、すべてのシステム ドライブを暗号化するために使用されます。 
[Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows) | 起動時にシステムの整合性を保護し、システムの整合性が本当に維持されているのを検証します。
[Windows Defender Credential Guard]( https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) | Windows Defender Credential Guard では、仮想化ベースのセキュリティを使用してシークレットを分離し、特権を持つシステム ソフトウェアだけがシークレットにアクセスできます。
[Microsoft Defender for Endpoint | エンドポイントの検出と応答](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) |     Microsoft マネージド デスクトップ セキュリティ操作は、アラートに応答し、エンドポイントの検出と対応を使用して脅威を修復するアクションを実行します。
[Microsoft Defender for Endpoint | 脅威の専門家](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts) | Microsoft マネージド デスクトップは、標的型攻撃通知を通じて脅威の専門家の分析情報とデータを統合します。 お客様は、このサービスを有効にする前に、追加の同意を提供する必要があります。  
[Microsoft Defender for Endpoint | 脅威と脆弱性の管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) | Microsoft マネージド デスクトップ サービス プランで将来使用するために必要です。
[Microsoft Defender for Endpoint | 攻撃表面の縮小](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) | 攻撃表面の縮小は、攻撃者によって悪用される危険なソフトウェア動作をターゲットにしています。
[Microsoft Defender for Endpoint | Exploit Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) | 悪用を使ってデバイスに感染し、悪用を軽減する手法をオペレーティング システムプロセスとアプリの両方に自動的に適用することで、マルウェアから保護します。
[Microsoft Defender for Endpoint | ネットワーク保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection) | ネットワーク保護は、Microsoft Defender SmartScreen のスコープを拡張して、低評価ソースへの接続を試みるすべての送信 HTTP トラフィックをブロックします。
[Microsoft Defender 改ざん防止](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) | Windows 改ざん防止は、ウイルス対策保護などのセキュリティ設定が変更されるのを防ぐために使用されます。
[Microsoft Defender ウイルス対策の動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) | マルウェアとして検出されない可能性があるファイルとプロセスの脅威を常にスキャンします。
[Microsoft Defender ウイルス対策クラウドによる保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus) | 新しい脅威や新たな脅威に対する動的なほぼ瞬時の自動保護を提供します。
[Microsoft Defender の最初のブロック](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus) | Windows が疑わしいファイルや不明なファイルを検出した場合の新しいマルウェアの検出とブロックを提供します。
[Microsoft Defender AV 望ましくない可能性があるアプリケーション](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) | 望ましくない可能性のあるアプリケーション (PUA) は、コンピューターの実行速度が遅くなる、予期しない広告を表示する、または最悪の場合は、予期しない、または望ましくない可能性のある他のソフトウェアをインストールするアプリをブロックするために使用されます。
[Windows Defenderファイアウォールのセキュリティが強化されている場合](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | デバイスのホスト ベースの、2 方向のネットワーク トラフィック フィルタリング、Windows Defender ファイアウォールは、ローカル デバイスに対して、またはローカル デバイスから送信される未承認のネットワーク トラフィックをブロックします。
[ユーザー アカウント制御](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works) | タスクまたはアクションで管理者アカウントの種類のアクセスが必要な場合、ユーザー アカウント制御はセキュリティで保護されたデスクトップに切り替わります。 Microsoft マネージド デスクトップ ユーザーには、登録時に Standard ユーザー アクセスが割り当てられます。 


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Enterprise Mobility + Security E3 と Azure Active Directory Premium P2 のすべての機能を使用して、MDM デバイスを管理できます。
Microsoft Cloud App Security |  このオプション機能は、Microsoft マネージド デスクトップで使用できます。
Azure Information Protection P2  | このオプション機能は、Microsoft マネージド デスクトップで使用できます。
