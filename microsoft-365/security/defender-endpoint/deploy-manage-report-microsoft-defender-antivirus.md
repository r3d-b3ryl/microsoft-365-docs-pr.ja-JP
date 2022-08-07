---
title: Microsoft Defender ウイルス対策の展開、管理、レポート
description: Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell、WMI を使用して Microsoft Defender ウイルス対策を展開および管理できます
keywords: 展開、管理、更新、保護、Microsoft Defender ウイルス対策
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.date: 08/05/2022
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 64a7bc6a95fa9f49da57bf14b6aebcb2e27c6d18
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67274663"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の展開、管理、レポート

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策 

**プラットフォーム**

- Windows

Microsoft Defender ウイルス対策の展開、管理、レポートは、さまざまな方法で行うことができます。

Microsoft Defender ウイルス対策クライアントは、Windows 10とWindows 11のコア部分としてインストールされているため、エンドポイントへのクライアントの従来の展開は適用されません。

ただし、ほとんどの場合、次の表に示すように、Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Defender for Cloud、またはグループ ポリシー オブジェクトを使用してエンドポイントで保護サービスを有効にする必要があります。

次の追加リンクも表示されます。

- 製品と保護の更新プログラムの管理を含む Microsoft Defender ウイルス対策保護の管理
- Microsoft Defender ウイルス対策保護に関するレポート

> [!IMPORTANT]
> ほとんどの場合、Windows 10またはWindows 11は、実行中で最新の別のウイルス対策製品が見つかると、Microsoft Defender ウイルス対策を無効にします。 Microsoft Defender ウイルス対策が機能する前に、サード パーティのウイルス対策製品を無効またはアンインストールする必要があります。 サードパーティのウイルス対策製品を再度有効またはインストールすると、Windows 10またはWindows 11自動的に Microsoft Defender ウイルス対策が無効になります。

ツール|デプロイ オプション (<a href="#fn2" id="ref2">2</a>)|管理オプション (ネットワーク全体の構成とポリシーまたはベースラインデプロイ) ([3](#fn3))|レポート オプション
---|---|---|---
Microsoft Intune|[Intuneにエンドポイント保護設定を追加する](/intune/endpoint-protection-configure)|[Intuneでデバイス制限設定を構成する](/intune/device-restrictions-configure)| [Intune コンソールを使用してデバイスを管理する](/intune/device-management)
Microsoft エンドポイント マネージャー ([1](#fn1))|[Endpoint Protection ポイント サイト システムの役割](/mem/configmgr/protect/deploy-use/endpoint-protection-site-role)を使用し、[カスタム クライアント設定で Endpoint Protection を有効にします](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)。|[既定とカスタマイズされたマルウェア対策ポリシー](/microsoft-365/security/office-365-security/configure-anti-malware-policies)とクライアント管理。|既定の[Configuration Manager監視ワークスペース](/mem/configmgr/apps/deploy-use/monitor-applications-from-the-console)と電子メール アラートを使用します。
グループ ポリシーと Active Directory (ドメイン参加済み)|グループ ポリシー オブジェクトを使用して構成変更を展開し、Microsoft Defender ウイルス対策が有効になっていることを確認します。|グループ ポリシー オブジェクト (GPO) を使用して[、Microsoft Defender ウイルス対策の更新オプションを構成](/microsoft-365/security/defender-endpoint/manage-protection-update-schedule-microsoft-defender-antivirus)し[、Windows Defender機能を構成します](/microsoft-365/security/defender-endpoint/configure-microsoft-defender-antivirus-features)。|エンドポイント レポートは、グループ ポリシーでは使用できません。 グループ ポリシーの一覧を生成して、設定またはポリシーが適用されていないかどうかを判断できます。
PowerShell|グループ ポリシー、Microsoft Endpoint Configuration Manager、または個々のエンドポイントに手動でデプロイします。|Defender モジュールで使用できる [Set-MpPreference] コマンドレットと [Update-MpSignature] コマンドレットを使用します。|[Defender モジュールで使用できる適切な Get- コマンドレットを](/powershell/module/defender)使用します。
Windows Management Instrumentation|グループ ポリシー、Microsoft Endpoint Configuration Manager、または個々のエンドポイントに手動でデプロイします。|[MSFT_MpPreference クラスの Set メソッドと、MSFT_MpSignature クラス](/previous-versions/windows/desktop/defender/set-msft-mppreference)[の Update メソッドを使用します](/previous-versions/windows/desktop/defender/update-msft-mpsignature)。|[MSFT_MpComputerStatus](/previous-versions/windows/desktop/defender/msft-mpcomputerstatus) クラスと、[Windows Defender WMIv2 プロバイダー](/windows/win32/wmisdk/wmi-providers)で関連付けられているクラスの get メソッドを使用します。
Microsoft Azure|[Visual Studio 仮想マシン構成を使用するか、Azure PowerShell コマンドレットを使用して、Azure portalに Azure のMicrosoft Antimalwareをデプロイします](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios)。 [Microsoft Defender for Cloud にエンドポイント保護をインストール](/azure/defender-for-cloud/endpoint-protection-recommendations-technical)することもできます。|[Azure PowerShell コマンドレットを使用してVirtual MachinesとCloud ServicesのMicrosoft Antimalwareを](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)構成するか、[コード サンプルを使用します](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)。|Azure PowerShell コマンドレットを使用して[Virtual MachinesとCloud ServicesにMicrosoft Antimalware](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)を使用して監視を有効にします。 また、Azure Active Directory の使用状況レポートを確認して、感染した可能性のあるデバイス レポートを含む疑わしいアクティビティを特定し、[Microsoft Defender ウイルス対策イベント][/microsoft-365/security/defender-endpoint/troubleshoot-microsoft-defender-antivirus] を報告し、そのツールを AAD のアプリとして追加するように SIEM ツールを構成することもできます。

1. <span id="fn1" />Microsoft エンドポイント マネージャー (Current Branch) と System Center 2012 Configuration Managerでは、一部の機能と機能 (特にクラウド配信保護に関連する機能) の可用性が異なります。 このライブラリでは、Windows 10、Windows 11、Windows Server 2016、Microsoft エンドポイント マネージャー (Current Branch) に重点を置きました。 主な違いを説明する表については、「 [Microsoft Defender ウイルス対策で Microsoft クラウド提供の保護を使用](cloud-protection-microsoft-defender-antivirus.md) する」を参照してください。 [(テーブルに戻る)](#ref2)

2. <span id="fn2" />Windows 10およびWindows 11では、Microsoft Defender ウイルス対策は、追加のクライアントまたはサービスをインストールまたは展開せずに使用できるコンポーネントです。 サード パーティのウイルス対策製品がアンインストールまたは古い (Windows Server 2016を除く) 場合、自動的に有効になります。 そのため、従来のデプロイは必要ありません。 ここでの展開とは、Microsoft Defender ウイルス対策コンポーネントがエンドポイントまたはサーバーで使用可能で有効になっていることを確認することです。 [(テーブルに戻る)](#ref2)

3. <span id="fn3" />製品と保護の更新プログラムの構成など、機能と保護の構成については、このライブラリの [「Microsoft Defender ウイルス対策機能の構成](configure-notifications-microsoft-defender-antivirus.md) 」セクションで詳しく説明します。 [(テーブルに戻る)](#ref2)

## <a name="in-this-section"></a>このセクションの内容

記事 | 説明
---|---
[Microsoft Defender ウイルス対策保護を展開して有効にする](deploy-microsoft-defender-antivirus.md) | クライアントはWindows 10またはWindows 11のコア 部分としてインストールされ、従来の展開は適用されませんが、Microsoft Endpoint Configuration Manager、Microsoft Intune、またはグループ ポリシー オブジェクトを使用してエンドポイントでクライアントを有効にする必要があります。
[Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md) | Microsoft Defender ウイルス対策を更新するには、エンドポイントでクライアントを更新する (製品の更新)、セキュリティ インテリジェンス (保護更新プログラム) の更新の 2 つの部分があります。 Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell、WMI を使用して、さまざまな方法でセキュリティ インテリジェンスを更新できます。
[Microsoft Defender ウイルス対策保護の監視とレポート](report-monitor-microsoft-defender-antivirus.md) | Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Operations Management Suite の Update Compliance アドイン、またはサード パーティの SIEM 製品 (Windows イベント ログを使用) を使用して、保護状態を監視し、エンドポイント保護に関するレポートを作成できます。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
    
