---
title: Microsoft Defender ウイルス対策のデプロイ、管理、レポート
description: Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell、WMI を使用してMicrosoft Defender ウイルス対策を展開および管理できます
keywords: デプロイ、管理、更新、保護、Microsoft Defender ウイルス対策
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 4e0d249f7805c47be55ec42f3362ca1952c20ca3
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788504"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策のデプロイ、管理、レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策 

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策のデプロイ、管理、レポートは、さまざまな方法で行うことができます。

Microsoft Defender ウイルス対策 クライアントはWindows 10とWindows 11のコア部分としてインストールされているため、エンドポイントへのクライアントの従来のデプロイは適用されません。

ただし、ほとんどの場合、Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Defender for Cloud、またはグループ ポリシーを使用してエンドポイントで保護サービスを有効にする必要があります。 次の表に示すオブジェクト。

次の追加リンクも表示されます。

- 製品と保護の更新の管理を含む、Microsoft Defender ウイルス対策保護の管理
- Microsoft Defender ウイルス対策保護に関するレポート

> [!IMPORTANT]
> ほとんどの場合、Windows 10またはWindows 11は、実行中で最新の別のウイルス対策製品が見つかると、Microsoft Defender ウイルス対策を無効にします。 Microsoft Defender ウイルス対策が機能する前に、サード パーティのウイルス対策製品を無効またはアンインストールする必要があります。 サードパーティのウイルス対策製品を再び有効またはインストールすると、Windows 10またはWindows 11自動的にMicrosoft Defender ウイルス対策が無効になります。

ツール|デプロイ オプション (<a href="#fn2" id="ref2">2</a>)|管理オプション (ネットワーク全体の構成とポリシーまたはベースラインデプロイ) ([3](#fn3))|レポート オプション
---|---|---|---
Microsoft Intune|[Intuneにエンドポイント保護設定を追加する](/intune/endpoint-protection-configure)|[Intuneでデバイス制限設定を構成する](/intune/device-restrictions-configure)| [Intune コンソールを使用してデバイスを管理する](/intune/device-management)
Microsoft エンドポイント マネージャー ([1](#fn1))|[Endpoint Protection ポイント サイト システムの役割][] と [カスタム クライアント設定でEndpoint Protectionを有効にする][] を使用します。|[既定およびカスタマイズされたマルウェア対策ポリシー][] と [クライアント管理][] を使用する|既定の [Configuration Manager監視ワークスペース][] と [電子メール アラート][]
グループ ポリシーと Active Directory (ドメイン参加済み)|グループ ポリシー オブジェクトを使用して構成変更をデプロイし、Microsoft Defender ウイルス対策が有効になっていることを確認します。|グループ ポリシー オブジェクト (GPO) を使用して [Microsoft Defender ウイルス対策の更新オプションを構成する][] と [Windows Defender機能の構成][]|エンドポイント レポートは、グループ ポリシーでは使用できません。 [グループ ポリシー] の一覧を生成して、設定またはポリシーが適用されていないかどうかを判断できます。][]
PowerShell|グループ ポリシー、Microsoft Endpoint Configuration Manager、または個々のエンドポイントに手動でデプロイします。|Defender モジュールで使用できる [Set-MpPreference] コマンドレットと [Update-MpSignature] コマンドレットを使用します。|適切な [Defender モジュールで使用可能な Get- コマンドレット][] を使用する
Windows Management Instrumentation|グループ ポリシー、Microsoft Endpoint Configuration Manager、または個々のエンドポイントに手動でデプロイします。|[MSFT_MpPreference クラスの Set メソッド][] と [MSFT_MpSignature クラスの Update メソッド][] を使用します。|[MSFT_MpComputerStatus][][] クラスと [Windows Defender WMIv2 Provider][] の関連クラスの get メソッドを使用します。
Microsoft Azure|Visual Studio[仮想マシン構成を使用するか、Azure PowerShellコマンドレットを使用して、Azure portalに Azure のMicrosoft Antimalwareをデプロイします](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios)。 [Microsoft Defender for Cloud* にエンドポイント保護をインストールすることもできます。](/azure/security-center/security-center-install-endpoint-protection)|[Azure PowerShell コマンドレットを使用してVirtual MachinesとCloud ServicesのMicrosoft Antimalwareを](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)構成するか、[コード サンプルを使用](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)する|Azure PowerShell コマンドレットを使用して[Virtual MachinesとCloud ServicesにMicrosoft Antimalware](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)を使用して監視を有効にします。 また、Azure Active Directoryの使用状況レポートを確認して、[感染した可能性のあるデバイス][] レポートを含む疑わしいアクティビティを特定し、[Microsoft Defender ウイルス対策 イベント][] を報告し、そのツールをAADでアプリとして追加するように SIEM ツールを構成することもできます。

1. <span id="fn1" />一部の機能と機能の可用性 (特にクラウド配信保護に関連) は、Microsoft エンドポイント マネージャー (Current Branch) と System Center 2012 Configuration Managerによって異なります。 このライブラリでは、Windows 10、Windows 11、Windows Server 2016、Microsoft エンドポイント マネージャー (Current Branch) に重点を置きました。 主な違いを説明する表については、「[Microsoft Defender ウイルス対策で Microsoft クラウド提供の保護を使用](cloud-protection-microsoft-defender-antivirus.md)する」を参照してください。 [(テーブルに戻る)](#ref2)

2. <span id="fn2" />Windows 10およびWindows 11では、Microsoft Defender ウイルス対策は、追加のクライアントまたはサービスのインストールまたは展開なしで使用できるコンポーネントです。 サード パーティのウイルス対策製品がアンインストールまたは古い (Windows Server 2016を除く) 場合、自動的に有効になります。 そのため、従来のデプロイは必要ありません。 ここでのデプロイとは、エンドポイントまたはサーバーでMicrosoft Defender ウイルス対策 コンポーネントが使用可能で有効になっていることを確認することです。 [(テーブルに戻る)](#ref2)

3. <span id="fn3" />製品と保護の更新プログラムの構成を含む機能と保護の構成については、このライブラリの[「Microsoft Defender ウイルス対策機能の構成](configure-notifications-microsoft-defender-antivirus.md)」セクションで詳しく説明します。 [(テーブルに戻る)](#ref2)

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
---|---
[Microsoft Defender ウイルス対策保護をデプロイして有効にする](deploy-microsoft-defender-antivirus.md) | クライアントはWindows 10またはWindows 11のコア部分としてインストールされており、従来のデプロイは適用されませんが、Microsoft Endpoint Configuration Manager、Microsoft Intune、またはエンドポイントでクライアントを有効にする必要があります。グループ ポリシー オブジェクト。
[Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md) | Microsoft Defender ウイルス対策を更新するには、エンドポイントでクライアントを更新する (製品の更新)、セキュリティ インテリジェンス (保護更新プログラム) の更新の 2 つの部分があります。 Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell、WMI を使用して、さまざまな方法でセキュリティ インテリジェンスを更新できます。
[Microsoft Defender ウイルス対策保護の監視とレポート](report-monitor-microsoft-defender-antivirus.md) | Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Operations Management Suite の Update Compliance アドイン、またはサード パーティの SIEM 製品 (Windows イベント ログを使用) を使用して、保護の状態を監視し、エンドポイント保護に関するレポートを作成できます。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
    
