---
title: 管理されていないWindows 10 PC と Mac を保護Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 管理されていないデバイスまたは持ち込み専用デバイス (BYOD) を保護するには、Microsoft 365 Business Premium。
ms.openlocfilehash: b3d783ba498337af7ff867fe749366abe1734da5
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331051"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs-in-microsoft-365-business-premium"></a>管理されていないWindows 10 PC と Mac を保護Microsoft 365 Business Premium

Microsoft Intune に登録することで、Windows 10 PC と Mac を管理できます。これにより、環境内のデータにアクセスする前に、正常で安全な状態を確保できます。 ただし、多くのキャンペーンや小規模企業には、組織によって管理されない独自のデバイス (BYOD) を持ち込むスタッフが含まれます。 これらの管理されていない PC および Mac については、この記事を使用して、最小限のセキュリティ機能が構成されていることを確認します。

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>コンピューターまたは Mac で実行Windows 10を保護する

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
PC または mac Windows 10が組織によって管理されていない場合は、必ずこれらのセキュリティ機能を構成してください。

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**デバイスの暗号化を有効にする**<p>

デバイスの暗号化は、さまざまなデバイスで利用Windows、データを暗号化することでデータを保護するのに役立ちます。 デバイスの暗号化を有効にした場合、承認された個人のみがデバイスとデータにアクセスできます。 手順 [については、「デバイスの暗号化を有効](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) にする」を参照してください。

 デバイスでデバイスの暗号化を利用できない場合は、代わりに標準 [の BitLocker 暗号化を](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 有効にできます。 (BitLocker は、このエディションではWindows 10 Homeできません)。 

**デバイスを保護するには、Windows セキュリティ**<p>
インストールされている場合Windows 10、最新のウイルス対策保護が提供Windows セキュリティ。 Windows 10 を初めて起動すると、Windows セキュリティ がオンで、マルウェア (悪意のあるソフトウェア)、ウイルス、セキュリティの脅威をスキャンして PC を保護するために積極的に支援します。 Windows セキュリティリアルタイム保護を使用して、PC でダウンロードまたは実行するすべてをスキャンします。

Windows Update では、自動的に Windows セキュリティの更新プログラムをダウンロードして、PC の安全を確保し、脅威から保護します。

以前のバージョンの Windows を使用している場合Microsoft Security Essentialsに移動するとWindows セキュリティ。 詳細については、「デバイスを保護[する」](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)を参照Windows セキュリティ。

**Windows ファイアウォールを有効にする**<p>
別のファイアウォールを有効Windows場合でも、常にファイアウォールを実行する必要があります。 ファイアウォールをWindowsすると、デバイス (およびネットワークがある場合) が、承認されていないアクセスに対してより脆弱になる可能性があります。 手順[については、「Windowsファイアウォールを有効または無効にする](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)」を参照してください。

## <a name="mac"></a>[Mac](#tab/Mac)

**FileVault を使用して Mac ディスクを暗号化する**<p>
ディスク暗号化は、デバイスが紛失または盗難に遭った場合にデータを保護します。 FileVault のフル ディスク暗号化は、起動ディスク上の情報への不正アクセスを防ぐのに役立ちます。 手順 [については、「FileVault を使用して Mac 上の起動ディスクを暗号化する」](https://support.apple.com/HT204837) を参照してください。

**マルウェアから Mac を保護する**<p>
Microsoft では、Mac に信頼性の高いウイルス対策ソフトウェアをインストールして使用する必要があります。 選択肢の一覧については、次の記事を参照してください。[ベスト Mac ウイルス対策 2019。](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)

また、信頼できるソースからのみソフトウェアを使用することで、マルウェアのリスクを軽減できます。 [セキュリティとプライバシー] &設定を使用すると、Mac にインストールされているソフトウェアのソースを指定できます。 詳細については、「マルウェアから [Mac を保護する」を参照してください](https://support.apple.com/kb/PH25087)。

**ファイアウォール保護を有効にする**<p>
ファイアウォールの設定を使用して、インターネットやネットワークに接続するときに他のコンピューターによって開始された不要な連絡先から Mac を保護します。 この保護がない場合、Mac は不正アクセスに対してより脆弱になる可能性があります。 手順 [については、アプリケーション ファイアウォール](https://support.apple.com/HT201642) に関するページを参照してください。
