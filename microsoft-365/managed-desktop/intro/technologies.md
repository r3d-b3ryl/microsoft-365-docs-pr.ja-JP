---
title: Microsoft マネージド デスクトップのテクノロジ
description: この記事では、Microsoft Managed Desktop で使用されるテクノロジとアプリの一覧を示します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 22371d22562960efdc50235657a08e15dba893d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920578"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft マネージド デスクトップのテクノロジ

この記事では、Microsoft Managed Desktop で使用されるテクノロジとアプリの一覧を示します。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise ライセンスは、すべての Microsoft マネージ デスクトップ ユーザーに必要です。 サービスのライセンス要件の詳細については [、「Microsoft Managed Desktop の前提条件」を参照してください](../get-ready/prerequisites.md)。

この記事では、必要なエンタープライズ ライセンスに含まれるコンポーネントの概要と、サービスが Microsoft Managed Desktop デバイスで各コンポーネントを使用する方法について説明します。 各領域の特定の役割と責任については、Microsoft Managed Desktop のドキュメントを通じて詳しく説明します。 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 または E5
 |
 --- | ---
Microsoft 365 Apps for enterprise (64 ビット) | これらのOfficeは、Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote のデバイスに同梱されます。<br><br>64 ビット版の Microsoft Project と Microsoft Visio は含まれていません。 ただし、これらのアプリケーションのインストールは Microsoft 365 Apps for enterprise インストールに依存しますので、Microsoft Managed Desktop は既定の Microsoft Intune 展開とセキュリティ グループを作成し、これらのアプリケーションをライセンスユーザーに展開するために使用できます。 詳細については [、「Microsoft マネージ デスクトップ デバイスに Microsoft Project または Microsoft Visio をインストールする」を参照してください](../get-started/project-visio.md)。
OneDrive |Azure Active Directory シングル サインオンは、ユーザーが OneDrive に初めてサインインするときに有効になります。<br><br>"Desktop"、"Document"、"Pictures" フォルダーの既知のフォルダー リダイレクトが含まれています。Microsoft Managed Desktop によって有効および構成されます。
ストア アプリ |    Microsoft Sway と Power BI はデバイスに同梱されません。 これらのアプリは、Microsoft Store からダウンロードできます。
Win32 アプリケーション |    Teams はデバイスと一緒に出荷されませんが、Microsoft によってパッケージ化され、Microsoft Managed Desktop デバイス用に提供されます。 Azure Information Protection Client はデバイスに同梱されませんが、展開用にパッケージ化できます。
Web アプリケーション |  Yammer、Office、Delve、Flow、StaffHub、PowerApps、Planner はデバイスに同梱されません。 ユーザーは、ブラウザーを使用してこれらのアプリケーションの Web バージョンにアクセスできます。


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint を使用した Windows 10 Enterprise E5 または E3
IT 管理者が次の設定を構成することをお勧めします。 これらの設定は、Microsoft Managed Desktop の一部として含まれるか、管理される必要はありません。

 |
 --- | ---
Windows Hello for Business | Microsoft Managed Desktop デバイスの強力な 2 要素認証にパスワードを置き換えるには、Windows Hello for Business を実装する必要があります。 詳細については [、「Windows Hello for Business」を参照してください](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。
アプリケーションの仮想化 | Intune Win32 アプリ管理クライアントを使用して、アプリケーション仮想化 (App-V) パッケージを展開できます。 詳細については [、「Application Virtualization 」を参照してください](/windows/application-management/app-v/appv-technical-reference)。
Microsoft 365 データ損失防止 | Microsoft 365 データ損失防止を実装して、機密性が高いと判断したアイテムに対して実行されるアクションを監視し、それらのアイテムの意図しない共有を防止する必要があります。 詳細については [、「Microsoft 365 データ損失防止」を参照してください](../../compliance/endpoint-dlp-learn-about.md)。


Microsoft Managed Desktop の一部として含まれる機能と管理機能:

 |
 --- | ---
BitLocker ドライブの暗号化 | BitLocker ドライブの暗号化は、すべてのシステム ドライブを暗号化するために使用されます。 詳細については [、「BitLocker ドライブの暗号化」を参照してください](/windows/security/information-protection/bitlocker/bitlocker-overview)。
Windows Defender System Guard | 起動時にシステムの整合性を保護し、システムの整合性が本当に維持されたと検証します。 詳細については、「System [Guard Windows Defender」を参照してください]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)。
Windows Defender Credential Guard | Windows Defender Credential Guard は仮想化ベースのセキュリティを使用してシークレットを分離し、特権システム ソフトウェアだけがアクセスできます。 詳細については、「System [Guard Windows Defender」を参照してください]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)。
エンドポイント向け Microsoft Defender - エンドポイントの検出と応答 | Microsoft Managed Desktop Security Operations はアラートに応答し、エンドポイント検出と応答を使用して脅威を修復するアクションを実行します。 詳細については [、「Microsoft Defender for Endpoint - Endpoint Detection and Response 」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)。
Microsoft Defender for Endpoint - Threat Experts | Microsoft Managed Desktop は、標的型攻撃通知を通じて脅威エキスパートの分析情報とデータを統合します。 このサービスを有効にする前に、追加の同意を提供する必要があります。 詳細については [、「Microsoft Defender for Endpoint - Threat Experts」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)。
エンドポイント向け Microsoft Defender - 脅威と脆弱性の管理 | Microsoft Managed Desktop サービス プランでの将来の使用に必要です。 詳細については [、「Microsoft Defender for Endpoint - Threat and Vulnerability Management」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。
エンドポイント向け Microsoft Defender - 攻撃表面の縮小 | 攻撃表面の縮小は、攻撃者によって悪用されるリスクの高いソフトウェアの動作をターゲットにしています。 詳細については [、「Microsoft Defender for Endpoint - Attack Surface Reduction 」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。
Microsoft Defender for Endpoint - Exploit Protection | エクスプロイトを使用してデバイスに感染し、オペレーティング システム プロセスとアプリの両方に悪用の軽減手法を自動的に適用することで、マルウェアから保護します。 詳細については [、「Microsoft Defender for Endpoint - Exploit Protection」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)。
Microsoft Defender for Endpoint - ネットワーク保護 | ネットワーク保護は、Microsoft Defender SmartScreen の範囲を拡大して、低評価ソースへの接続を試みるすべての送信 HTTP および HTTPS トラフィックをブロックします。 詳細については [、「Microsoft Defender for Endpoint - Network Protection」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/network-protection)。
Microsoft Defender タンパープロテクション | Windows タンパープロテクションは、ウイルス対策保護などのセキュリティ設定が変更されるのを防ぐために使用されます。 詳細については [、「Microsoft Defender タンパー プロテクション」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)。
Microsoft Defender ウイルス対策の動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護 | 常にファイルをスキャンし、マルウェアとして検出されない可能性のある脅威を処理します。 詳細については [、「Microsoft Defender ウイルス対策の動作ベース、ヒュー]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)リスティック、リアルタイムのウイルス対策保護」を参照してください。
Microsoft Defender ウイルス対策クラウド配信の保護 | 新しい脅威や新しい脅威に対する動的なほぼ瞬時の自動保護を提供します。 詳細については [、「Microsoft Defender Antivirus Cloud-delivered Protection」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)。
Microsoft Defender "一目でブロックする" | Windows が疑わしいファイルまたは不明なファイルを検出した場合に、新しいマルウェアの検出とブロックを提供します。 詳細については [、「Microsoft Defender Block at first sight」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)。
Microsoft Defender AV 潜在的に望ましくないアプリケーション | 望ましくない可能性のあるアプリケーションは、コンピューターの動作が遅くなる、予期しない広告を表示する、または最悪の場合は予期しない、または望ましくない可能性のある他のソフトウェアをインストールするアプリをブロックするために使用されます。 詳細については、「Microsoft Defender AV 潜在的に望ましくない [アプリケーション」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)。
Windows Defenderセキュリティを使用したファイアウォール | デバイスのホスト ベースの、2 方向ネットワーク トラフィック フィルタリング、Windows Defender ファイアウォールは、ローカル デバイスに流れ込む、またはローカル デバイスから送信される未承認のネットワーク トラフィックをブロックします。 詳細については、「Advanced [Security Windows Defenderファイアウォール」を参照してください](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。
ユーザー アカウント制御 | タスクまたはアクションで管理者アカウントタイプのアクセスが必要な場合、ユーザー アカウント制御は Secure Desktop に切り替わります。 Microsoft Managed Desktop ユーザーには、登録時に Standard ユーザー アクセスが割り当てられます。 詳細については、「User [Account Control」を参照してください](/windows/security/identity-protection/user-account-control/how-user-account-control-works)。


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Enterprise Mobility + Security E3 および Azure Active Directory Premium P2 のすべての機能を使用して MDM デバイスを管理できます。
Microsoft Cloud App Security |  このオプション機能は、Microsoft Managed Desktop と一緒に使用できます。
Azure Information Protection P2  | このオプション機能は、Microsoft Managed Desktop と一緒に使用できます。