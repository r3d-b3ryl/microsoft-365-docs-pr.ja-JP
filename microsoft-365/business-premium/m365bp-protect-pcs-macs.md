---
title: Microsoft 365 Business Premium でアンマネージド Windows PC と Mac を保護する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
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
description: Microsoft 365 Business Premium を使用して、管理されていないデバイスまたは持ち込みデバイス (BYOD) をサイバー攻撃から保護します。 Windows PC と Mac のサイバーセキュリティを設定する方法。
ms.openlocfilehash: 5a1239f84e801c6327eb18c1049e410cc0859bdb
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66631774"
---
# <a name="protect-unmanaged-windows-pcs-and-macs-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium でアンマネージド Windows PC と Mac を保護する

目標として、Microsoft Intune に登録されていないアンマネージド Windows 10 PC および Mac の保護を作成することに重点を置いて説明します。 中小企業やキャンペーンには、各自のデバイス (BYOD) を持ち込むスタッフがいる可能性があり、これらのデバイスは管理されていない可能性があります。 BYOD には、個人所有の電話、タブレット、PC が含まれます。

>[!NOTE]
>BYOD ユーザーは、これらのデバイスを登録し、会社のリソースへのアクセスを受け取るには、それぞれポータル サイト アプリをインストールして実行する必要があります。

すべての BYOD デバイスで最小限のセキュリティ機能が構成されるように、現場のユーザーがこれらのガイドラインに従っていることを確認することが重要です。

## <a name="windows-10-or-11"></a>[Windows 10 または 11](#tab/Windows10-11)

## <a name="windows-10-or-11"></a>Windows 10 または 11

### <a name="turn-on-device-encryption"></a>デバイスの暗号化を有効にする

デバイスの暗号化は、さまざまな Windows デバイスで使用でき、暗号化によってデータを保護するのに役立ちます。 デバイスの暗号化を有効にすると、承認された個人のみがデバイスとデータにアクセスできるようになります。 手順については、「[デバイス暗号化をオンする](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)」をご覧ください。

 デバイスでデバイスの暗号化を使用できない場合は、代わりに標準の [BitLocker 暗号化](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)を有効にできます。 (BitLocker は、Windows 10 Home エディションでは使用できません)。 

### <a name="protect-your-device-with-windows-security"></a>デバイスを Windows セキュリティで保護する

Windows 10 または 11 をお使いの場合は、Windows セキュリティを使用した最新のウイルス対策保護を利用できます。 Windows 10 を初めて立ち上げるときは、Windows セキュリティが有効になっており、マルウェア (悪意のあるソフトウェア)、ウイルス、およびセキュリティの脅威を積極的にスキャンして PC を保護します。 Windows セキュリティは、リアルタイム保護を使用して、ダウンロードされたアイテム、または PC で実行されるアイテムをすべてスキャンします。

Windows Update では、自動的に Windows セキュリティの更新プログラムをダウンロードして、PC の安全を確保し、脅威から保護します。

以前のバージョンの Windows を使用していて、Microsoft Security Essentials を使用している場合は、Windows セキュリティに移行することをお勧めします。 詳細については、「[Windows セキュリティでデバイスを保護する](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)」を参照してください。

### <a name="turn-on-windows-defender-firewall"></a>Windows Defender ファイアウォールを有効にする

別のファイアウォールが有効な場合でも、Windows Defender ファイアウォールを常に実行する必要があります。 Windows Defender ファイアウォールをオフにすると、デバイス (およびお持ちの場合はネットワーク) が攻撃を受けやすくなります。 手順については、「[Windows ファイアウォールをオン/オフにする](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)」を参照してください。

## <a name="next-mission"></a>次のミッション

ミッションが完了しました。では、[フィッシングやその他の攻撃に対するメール システムをセキュリティで保護する方法](m365bp-protect-email-overview.md)について説明します。

## <a name="macos"></a>[macOS](#tab/macOS)

## <a name="macos"></a>macOS

### <a name="use-filevault-to-encrypt-your-mac-disk"></a>FileVault を使用して、Mac のディスクを暗号化する

ディスクを暗号化すると、デバイスの紛失時または盗難時にデータが保護されます。 FileVault のディスク全体の暗号化を行うと、スタートアップ ディスクの情報に対する不正アクセスを防止するのに役立ちます。 手順については、「[FileVault を使用して Mac のスタートアップ ディスクを暗号化する](https://support.apple.com/HT204837)」を参照してください。

### <a name="protect-your-mac-from-malware"></a>Mac をマルウェアから保護する

Microsoft は、信頼性の高いウイルス対策ソフトウェアを Mac にインストールして使用することをお勧めします。 選択肢の一覧については、「[Best Mac ウイルス対策 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)」をご覧ください。

信頼できる発行元のみのソフトウェアを使用することにより、マルウェアの危険性を削減できます。 セキュリティとプライバシーの設定では、Mac にインストールされるソフトウェアの発行元を指定できます。 詳細については、「[マルウェアから Mac を保護する](https://support.apple.com/kb/PH25087)」を参照してください。

### <a name="turn-on-firewall-protection"></a>ファイアウォールの保護を有効にする

インターネットやネットワークに接続している場合は、ファイアウォールの設定を使用して、別のコンピューターが開始した不要な連絡先から Mac を保護します。 この保護がない場合は、お使いの Mac が攻撃に対してより脆弱になる可能性があります。 手順については、「[アプリケーション ファイアウォールについて](https://support.apple.com/HT201642)」を参照してください。

## <a name="next-mission"></a>次のミッション

ミッションが完了しました。では、[フィッシングやその他の攻撃に対するメール システムをセキュリティで保護する方法](m365bp-protect-email-overview.md)について説明します。