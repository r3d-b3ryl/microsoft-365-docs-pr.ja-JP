---
title: Microsoft 365 Business Premium のセットアップ
description: 詳細については、「設定方法」を参照Microsoft 365 Business Premium
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/01/2022
ms.service: o365-administration
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 5b6f187f93e8a135bfb67c78509553d2963b011b
ms.sourcegitcommit: b67385243fb56ad20f2a6f1c40be46f5691c1c2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63527816"
---
# <a name="set-up-microsoft-365-business-premium"></a>Microsoft 365 Business Premium のセットアップ

ユーザー設定と構成には、いくつかのオプションMicrosoft 365 Business Premium。 次の操作を実行できます。

- [基本的なセットアップと構成にガイド付きセットアップ エクスペリエンスを使用する](#guided-process-for-basic-setup)
- [パートナー (CSP) などのパートナー Microsoft クラウド ソリューション プロバイダー作業する](#work-with-a-microsoft-partner)
- [セットアップ プロセスを手動で実行する](#manual-setup-and-configuration)


この記事をガイドとして使用します。

## <a name="guided-process-for-basic-setup"></a>基本的なセットアップのガイド付きプロセス

Microsoft 365 Business Premiumセットアップのガイド付きプロセスが含まれています。 タスクには、カスタム ドメインへの接続、ユーザーの追加、ライセンスの割り当て、モバイル デバイスへの Outlook のインストール、データ保護設定の確認、モバイル アプリ保護ポリシーの適用が含まれます。 

ガイド付きセットアップの動作を確認するには、次のビデオをご覧ください。 <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE471FJ?autoplay=false]

ガイド付きセットアップが完了したら、セキュリティとコンプライアンスの機能が適切にセットアップおよび適用されていることを確認するために、追加の手順を実行する必要があります。 手順の概要を次に示します。

- [デバイスWindows保護](m365bp-secure-windows-devices.md)
- [アプリMicrosoft 365展開](../admin/setup/install-applications.md)
- [新しい Defender for Business 機能のセットアップと構成](../security/defender-business/mdb-setup-configuration.md)

[ガイド付きセットアップ プロセスと [セットアップ] ページの違いについて説明します](../admin/setup/o365-setup-wizard-and-setup-page.md)。

> [!TIP]
> 設定と構成の詳細については、次のセクションを参照Microsoft 365 Business Premium。


## <a name="work-with-a-microsoft-partner"></a>Microsoft パートナーとの作業

Microsoft には、サービスを販売する権限を持つソリューション プロバイダーの一覧が含Microsoft 365 Business Premium。 

地域でソリューション プロバイダーを検索するには、次の手順を実行します。

1. [Microsoft ソリューション **プロバイダー] ページ () に移動** します [https://www.microsoft.com/solution-providers](https://www.microsoft.com/solution-providers)。
 
2. 検索ボックスに、場所と会社のサイズを入力します。 

3. [製品、 **サービス、スキル、業種** の検索] ボックスで、[入 `Microsoft 365`れる] をクリックし、[移動] を **選択します**。

4. 結果の一覧を確認します。 プロバイダーを選択して、専門知識と提供するサービスの詳細を確認します。

「パートナー [またはリセラーを探す」も参照してください](../admin/manage/find-your-partner-or-reseller.md)。

## <a name="manual-setup-and-configuration"></a>手動セットアップと構成

セットアップと構成プロセスを手動で完了する場合は、次の表をガイドとして使用します。

| 段階  | タスク  | 追加情報  |
|---------|---------|---------|
| **計画**     | セットアップと構成プロセスを計画する  | [Microsoft 365 for business のセットアップを計画](../admin/setup/plan-your-setup.md)   |
|  | システム要件を確認する | [Microsoft 365 Business Premium要件](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:overviewtab) |
| **基本的なセットアップ**     | カスタム ドメイン (カスタム ドメインなど) `rob@contoso.com` を使用Microsoft 365 | [Microsoft 365 にドメインを追加する](../admin/setup/add-domain.md) |
|      | ユーザーを追加し、ライセンスを割り当Microsoft 365      | [ユーザーを追加して同時にライセンスを割り当てる](../admin/add-users/add-users.md)        |
|  | 次のような特定の機能を実行するユーザーに管理者の役割を割り当てます。 <br/>- 機能の管理<br/>- ユーザー アカウントの管理<br/>- デバイスの管理<br/>- 組織のセキュリティおよびコンプライアンス情報の表示または管理 | [管理者ロールの詳細](../admin/add-users/about-admin-roles.md) <br/><br/> [管理者の役割を割り当てる](../admin/add-users/assign-admin-roles.md)  |
|  | インストールMicrosoft 365 Apps (Word、Excel、PowerPointなど) | [Office アプリケーションのインストール](../admin/setup/install-applications.md) |
| **組織のセキュリティ保護** | サブスクリプションをセキュリティで保護するには、トップ 10 Microsoft 365してください。 |  [ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../admin/security-and-compliance/secure-your-business-data.md) |
|  | ユーザーがユーザーにサインインするときに、すべてのユーザーに追加の検証方法を使用Microsoft 365 | [多要素認証を設定する](../admin/security-and-compliance/set-up-multi-factor-authentication.md) | 
| **電子メールとコンテンツの保護** |  悪意のある偽装ベースのフィッシング攻撃や他のフィッシング攻撃から保護するために高度なフィッシング対策保護を設定する | [フィッシング攻撃からメールを保護する](../admin/security-and-compliance/secure-your-business-data.md) |
|   | 悪意のあるセーフから組織を保護するための添付ファイルの設定 | [悪意のある添付ファイルや添付ファイルから保護セーフする](../admin/security-and-compliance/secure-your-business-data.md) |
|  | 電子メール セーフドキュメント内の悪意のある Web サイト (URL) から保護するためのリンクOffice設定する | [リンクのセーフ設定](../admin/security-and-compliance/secure-your-business-data.md) |
|  | 機密情報を共有から保護するためのデータ損失防止ポリシーを設定する | [コンプライアンス機能のセットアップ](../admin/security-and-compliance/set-up-compliance.md) |
| **デバイスの管理と保護** | 組織のデバイスを保護Windowsする | [セキュリティで保護Windowsデバイス](m365bp-secure-windows-devices.md) <br/><br/>[デバイスのアプリケーション保護設定を設定またはWindows 10する](../admin/devices/protection-settings-for-windows-10-devices.md) |
|   | モバイル Microsoft 365アプリのセキュリティ保護 | [Android または iOS デバイスのアプリ保護設定を設定する](../admin/devices/app-protection-settings-for-android-and-ios.md) |
|  | Microsoft Defender for Business をセットアップする (テナントで使用可能な場合) | [Microsoft Defender for Business の概要](../security/defender-business/mdb-overview.md)<br/><br/>[ウィザードを使用して Defender for Business をセットアップする](../security/defender-business/mdb-use-wizard.md) |
| **ファイルストレージとコンテンツの移行** | ファイル ストレージのセットアップと、組織での共有の動作方法 | [ファイルストレージと共有を設定する方法は、Microsoft 365](../admin/setup/set-up-file-storage-and-sharing.md) |
| | メールと連絡先のインポートまたは移行 | [Microsoft 365 へのメールと連絡先の移行](../admin/setup/migrate-email-and-contacts-admin.md) |
|  | すべてのユーザーがアクセスする必要がある会社のファイルをSharePoint (通常SharePointファイル共有またはネットワーク ドライブの使用を置き換えます) | [ファイルをファイルに移動SharePoint](../admin/setup/files-to-sharepoint.md) |
|  | 個人用作業ファイルや機密性の高いビジネス ファイルなど、既存の作業ファイルを別の作業OneDrive | [ファイルをファイルに移動OneDrive](../admin/setup/files-to-onedrive.md) |
| **管理者とセキュリティ チームのトレーニング** | 管理センターの使い方について | [Microsoft 365 管理センターの概要](../admin/admin-overview/admin-center-overview.md) |
|  | 管理者向け無料のトレーニング ビデオ ライブラリMicrosoft 365する | [管理者トレーニング ビデオ ライブラリ](../admin/admin-video-library.yml)  |
|  | ポータルを使用するMicrosoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) | [ポータルの使用Microsoft 365 Defenderする](../security/defender-business/mdb-get-started.md) |

> [!TIP]
> いくつかのヘルプが必要ですか? ビジネス アシストの[取得を検討Microsoft 365](https://support.microsoft.com/en-us/office/business-assist-for-microsoft-365-37deb8fe-61cc-4cf9-9ad1-1c8d93475070)

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Business の概要](../security/defender-business/mdb-overview.md) (現在、Microsoft Defender for Business にMicrosoft 365 Business Premium!

- [ビジネス サブスクリプションと課金ドキュメント](../commerce/index.yml)

- [Microsoft Microsoft 365 Lighthouse](../lighthouse/m365-lighthouse-overview.md)の概要 (Microsoft の CSP 用)

- [ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../admin/security-and-compliance/secure-your-business-data.md)
