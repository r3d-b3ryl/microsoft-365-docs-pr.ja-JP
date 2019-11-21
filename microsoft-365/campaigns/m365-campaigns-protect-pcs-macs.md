---
title: 管理されていない Windows 10 Pc および Mac を保護する
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 を使用した、キャンペーンに対するフィッシングやその他の攻撃から保護します。
ms.openlocfilehash: 93bb36f115ee5f83e07ac9623c852fec4dbf205f
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753626"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>管理されていない Windows 10 Pc および Mac を保護する

Windows 10 Pc および Mac を Microsoft Intune に登録することによって管理できます。これにより、環境内のデータにアクセスする前に、それらを正常かつ安全な状態に保つことができます。 しかし、多くのキャンペーンおよび小規模企業には、組織で管理されていない独自のデバイス (byod) を持っているスタッフが含まれています。 これらの管理されていない Pc および Mac では、この記事を使用して最小限のセキュリティ機能が構成されていることを確認してください。 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Windows 10 または Mac を実行しているコンピューターを保護する

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Windows 10 PC または Mac が組織で管理されていない場合は、必ずこれらのセキュリティ機能を構成してください。

## <a name="windows-10tabwindows10"></a>[Windows 10](#tab/Windows10)
**デバイスの暗号化を有効にする**<p>

デバイスの暗号化は、さまざまな Windows デバイスで使用でき、暗号化によってデータを保護します。 デバイスの暗号化を有効にすると、承認されたユーザーのみがデバイスとデータにアクセスできるようになります。 手順については、「 [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 」を参照してください。

 デバイスの暗号化がデバイスで使用できない場合は、代わりに標準の[BitLocker 暗号化](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)を有効にすることができます。 (Windows 10 Home edition で BitLocker を使用することはできません。) 


**Windows セキュリティを使用してデバイスを保護する**<p>
Windows 10 を使用している場合は、Windows セキュリティによる最新のウイルス対策保護が得られます。 Windows 10 を初めて起動すると、Windows セキュリティがオンになり、マルウェア (悪意のあるソフトウェア)、ウイルス、およびセキュリティの脅威をスキャンすることにより、PC の保護が積極的に促進されます。 Windows セキュリティは、リアルタイム保護を使用して、PC でダウンロードまたは実行されたすべての情報をスキャンします。

Windows Update は、PC の安全性を確保して脅威から保護するために、Windows セキュリティの更新プログラムを自動的にダウンロードします。

以前のバージョンの Windows を使用していて、Microsoft Security Essentials を使用している場合は、Windows セキュリティに移行することをお勧めします。 詳細については、「 [Windows セキュリティでデバイスを保護](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)する」を参照してください。

**Windows ファイアウォールを有効にする**<p>
別のファイアウォールが有効になっている場合でも、Windows ファイアウォールを常に実行する必要があります。 Windows ファイアウォールを無効にすると、デバイス (とネットワークがある場合は、そのデバイスが許可されていないアクセスに対して脆弱になることがあります。 手順について[は、「Windows ファイアウォールの有効化または無効化](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)」を参照してください。

## <a name="mactabmac"></a>[Mac](#tab/Mac)
**FileVault を使用して Mac ディスクを暗号化する**<p>
ディスクの暗号化は、デバイスの紛失や盗難時にデータを保護します。 FileVault の完全な暗号化によって、スタートアップディスクの情報に対する権限のないアクセスを防ぐことができます。 手順については[、「Use FileVault to encrypt the startup disk In Mac](https://support.apple.com/HT204837) 」を参照してください。

**マルウェアから mac を保護する**<p>
Microsoft は、信頼性の高いウイルス対策ソフトウェアを Mac にインストールして使用することをお勧めします。 選択肢の一覧については、次の記事を参照してください。[最適な Mac ウイルス対策 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。

また、信頼できるソースからのソフトウェアのみを使用してマルウェアのリスクを軽減することもできます。 [セキュリティの & プライバシー設定] の設定では、Mac にインストールされているソフトウェアのソースを指定できます。 詳細については、「[マルウェアから Mac を保護](https://support.apple.com/kb/PH25087)する」を参照してください。

**ファイアウォール保護を有効にする**<p>
インターネットまたはネットワークに接続しているときに他のコンピューターによって開始された不要な連絡先から Mac を保護するには、ファイアウォールの設定を使用します。 この保護を使用しないと、Mac が権限のないアクセスに対して脆弱になる可能性があります。 手順に[ついては、「アプリケーションファイアウォールについ](https://support.apple.com/HT201642)て」を参照してください。
