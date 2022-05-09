---
title: Microsoft Defender ウイルス対策とOffice 365 (OneDriveを含む) - ランサムウェアやサイバー脅威からの保護の強化
description: OneDriveを含むOffice 365は、Microsoft Defender ウイルス対策と素晴らしく連携します。 詳細については、この記事を参照してください。
keywords: Windows Defender, ウイルス対策, Office 365, onedrive, 復元, ランサムウェア
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 1690a100a2743d35bc85f116398d94325ad47fbc
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788460"
---
# <a name="better-together-microsoft-defender-antivirus-and-office-365"></a>ベストな組み合わせ: Microsoft Defender ウイルス対策と Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策
- Microsoft 365

**プラットフォーム**
- Windows

次のことが既にわかっている場合があります。

- **Microsoft Defender ウイルス対策は、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威からWindows デバイスを保護します**。 Microsoft Defender ウイルス対策は、完全で継続的な保護であり、Windows 10とWindows 11に組み込まれており、準備が整いました。 [Microsoft Defender ウイルス対策は次世代の保護です](./microsoft-defender-antivirus-in-windows-10.md)。 

- **Office 365には、改ざん、スパム対策、マルウェア対策の保護が含まれます**。 Office 365サブスクリプションを使用すると、すべてのデバイスで、Premium メールと予定表、Office アプリ、1 TB のクラウド ストレージ (OneDrive 経由)、高度なセキュリティが提供されます。 これは、家庭ユーザーとビジネス ユーザーに当てはまります。 また、ビジネス ユーザーであり、組織がOffice 365 E5を使用している場合は、Office 365による[脅威から保護](/microsoft-365/security/office-365-security/protect-against-threats)Microsoft Defender for Office 365通じて、さらに保護を強化できます。

- **Office 365に含まれるOneDriveを使用すると、ファイルやフォルダーをオンラインで保存し、必要に応じて共有できます**。 OneDriveに格納されているユーザー (仕事や楽しみのために) と共同編集ファイルと連携できます。 すべてのデバイス (PC、スマートフォン、タブレット) でファイルにアクセスすることもできます。 [OneDriveで共有を管理します](/OneDrive/manage-sharing)。

**しかし、Office 365と共にMicrosoft Defender ウイルス対策を使用する適切なセキュリティ上の理由があることをご存知でした** か? 2 つを以下に示します。

 1. [ランサムウェアの保護と回復を取得します](#ransomware-protection-and-recovery)。

 2. [統合とは、より優れた保護を意味します](#integration-means-better-protection)。

詳細については、次のセクションを参照してください。

## <a name="ransomware-protection-and-recovery"></a>ランサムウェアの保護と回復

ファイルを[OneDrive](/onedrive)に保存し、デバイスでランサムウェアの脅威が検出[Microsoft Defender ウイルス対策](./microsoft-defender-antivirus-in-windows-10.md)、次のことが発生します。

1. **脅威について説明されます**。 (組織が[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)を使用している場合は、セキュリティ運用チームにも通知されます)。

2. **Microsoft Defender ウイルス対策、(および組織のセキュリティ チーム) がデバイスからランサムウェアを削除するのに役立ちます**。 (組織でMicrosoft Defender for Endpointを使用している場合、セキュリティ運用チームは他のデバイスが感染しているかどうかを判断し、適切なアクションを実行することもできます)。

3. **OneDriveでファイルを回復するオプションが表示** されます。 OneDrive ファイルの復元機能を使用すると、ランサムウェア攻撃が発生する前の状態にOneDriveファイルを回復できます。 [ランサムウェアの検出とファイルの回復に関するページを参照してください](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)。

時間と手間を省くことができると考えてください。 

## <a name="integration-means-better-protection"></a>統合とは、保護の強化を意味します

Microsoft Defender for Office 365 Microsoft Defender for Endpointと統合すると、組織の保護が強化されます。 次の操作を実行してください。

- [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp)は、Office ドキュメント内の電子メール メッセージ、電子メールの添付ファイル、リンク (URL) に発生する悪意のある脅威から組織を保護します。

    および

- [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)は、サイバー脅威からデバイスを保護し、高度な攻撃とデータ侵害を検出し、セキュリティ インシデントを自動化し、セキュリティ体制を改善します。

    だから

- 統合が有効になると、セキュリティ運用チームは、検出された URL または電子メール メッセージの受信者によって使用されるデバイスの一覧と、それらのデバイスの最近のアラートを<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に表示できます。

まだ行っていない場合は、[Microsoft Defender for EndpointとMicrosoft Defender for Office 365を統合](/microsoft-365/security/office-365-security/integrate-office-365-ti-with-mde)します。

## <a name="more-good-reasons-to-use-onedrive"></a>OneDriveを使用するその他の正当な理由

ランサムウェアからの保護は、ファイルをOneDriveに配置する大きな理由の 1 つです。 また、このビデオにまとめられているいくつかの正当な理由があります。 <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/70b4d256-46fb-481f-ad9b-921ef5fd7bed]

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="want-to-learn-more-see-these-resources"></a>詳細な情報をご希望ですか? 次のリソースを参照してください。

- [OneDrive](/onedrive)

- [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp)

- [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)


