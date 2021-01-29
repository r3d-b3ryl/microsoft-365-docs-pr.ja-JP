---
title: 非管理対象 Windows 10 PC と Mac の保護
f1.keywords:
- NOCSH
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 で管理されていないデバイスや持ち込みデバイス (BYOD) を保護します。
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044386"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>非管理対象 Windows 10 PC と Mac の保護

Windows 10 PC と Mac を Microsoft Intune に登録することで管理できます。これにより、環境内のデータにアクセスする前に、Windows 10 PC と Mac が正常で安全な状態を確保できます。 ただし、多くのキャンペーンや小規模企業には、組織で管理されない独自のデバイス (BYOD) を持ち込むスタッフが含まれます。 これらの非管理対象 PC と Mac の場合は、この記事を使用して、最小セキュリティ機能が構成されていることを確認します。

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Windows 10 または Mac を実行しているコンピューターを保護する

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Windows 10 PC または Mac が組織によって管理されていない場合は、必ずこれらのセキュリティ機能を構成してください。

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**デバイスの暗号化を有効にする**<p>

デバイスの暗号化は、さまざまな Windows デバイスで利用できます。また、データを暗号化することでデータを保護するのに役立ちます。 デバイスの暗号化を有効にした場合、承認された個人のみがデバイスとデータにアクセスできます。 手順 [については、「デバイスの暗号化を有効にする](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 」をご覧ください。

 デバイスでデバイスの暗号化を利用できない場合は、代わりに標準的な [BitLocker 暗号化を](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 有効にできます。 (BitLocker は Windows 10 Home エディションでは使用できません)。 

**Windows セキュリティでデバイスを保護する**<p>
Windows 10 をお持ちの場合は、Windows セキュリティによる最新のウイルス対策保護が提供されます。 Windows 10 を初めて起動すると、Windows セキュリティが有効にされ、マルウェア (悪意のあるソフトウェア)、ウイルス、セキュリティの脅威をスキャンして PC を保護できます。 Windows セキュリティでは、リアルタイム保護を使用して、PC でダウンロードまたは実行したすべてをスキャンします。

Windows Update では、自動的に Windows セキュリティの更新プログラムをダウンロードして、PC の安全を確保し、脅威から保護します。

以前のバージョンの Windows を使用している場合はMicrosoft Security Essentials Windows セキュリティに移行すると良い方法です。 詳しくは [、Windows セキュリティを使ったデバイスの保護に関するヘルプをご覧ください](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)。

**Windows ファイアウォールを有効にする**<p>
別のファイアウォールが有効になっている場合でも、常に Windows ファイアウォールを実行する必要があります。 Windows ファイアウォールをオフにした場合、デバイス (およびネットワークがある場合) が未承認のアクセスに対して脆弱になる可能性があります。 手順 [については、「Windows ファイアウォールをオンまたはオフにする](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) 」を参照してください。

## <a name="mac"></a>[ Mac ](#tab/Mac)

**FileVault を使用して Mac ディスクを暗号化する**<p>
ディスク暗号化は、デバイスの紛失時や盗難時にデータを保護します。 FileVault のフル ディスク暗号化は、スタートアップ ディスク上の情報への不正なアクセスを防ぐのに役立ちます。 手順 [については、「FileVault を使って Mac の](https://support.apple.com/HT204837) スタートアップ ディスクを暗号化する」をご覧ください。

**マルウェアから Mac を保護する**<p>
Microsoft では、Mac に信頼性の高いウイルス対策ソフトウェアをインストールして使用してください。 選択肢の一覧については、次の記事を参照してください: [最適な Mac ウイルス対策 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)。

また、信頼できるソースからのみソフトウェアを使用することで、マルウェアのリスクを軽減できます。 [セキュリティとプライバシー] &設定では、Mac にインストールされているソフトウェアのソースを指定できます。 詳しくは、「Mac を [マルウェアから保護する」をご覧ください](https://support.apple.com/kb/PH25087)。

**ファイアウォール保護を有効にする**<p>
ファイアウォール設定を使用して、インターネットまたはネットワークに接続するときに、他のコンピューターによって開始された不要な連絡先から Mac を保護します。 この保護を使用しない場合、Mac は承認されていないアクセスに対してより脆弱になる可能性があります。 手順 [については、アプリケーション ファイアウォール](https://support.apple.com/HT201642) に関するページを参照してください。
