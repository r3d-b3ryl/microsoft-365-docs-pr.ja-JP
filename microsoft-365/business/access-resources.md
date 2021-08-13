---
title: ビジネス向け Azure AD参加デバイスからオンプレミス リソースにMicrosoft 365する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: ビジネス アプリの回線、ファイル共有、プリンターなど、オンプレミスのリソースにアクセスする方法について、Azure Active DirectoryデバイスWindows 10します。
ms.openlocfilehash: 49d7150adb8bcb0dd611e7dce10ee92d3de1755dbe8662e454c9afcca2055e69
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53809472"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Azure に参加しているデバイスからオンプレミスADにアクセスMicrosoft 365 Business Premium

この記事は、このMicrosoft 365 Business Premium。

参加Windows 10デバイスAzure Active Directory、Microsoft 365 アプリなど、すべてのクラウドベースのリソースにアクセスできます。Microsoft 365 Business Premium。 また、業務 (LOB) アプリ、ファイル共有、プリンターなど、オンプレミスのリソースへのアクセスを許可することもできます。 アクセスを許可するには[、Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect)を使用して、オンプレミスの Active Directory と同期Azure Active Directory。

詳細については、「デバイス管理の概要」を参照[Azure Active Directory。](/azure/active-directory/device-management-introduction)
手順は、次のセクションでも要約されています。

## <a name="run-azure-ad-connect"></a>Azure の実行AD Connect

以下の手順を実行して、組織の Azure ADに参加しているデバイスがオンプレミス のリソースにアクセスできます。

1. ローカル Active Directory から Azure Active Directory にユーザー、グループ、連絡先を同期するには、「ディレクトリ同期のセットアップ」の説明に従って、ディレクトリ同期ウィザードと Azure AD Connect[を](../enterprise/set-up-directory-synchronization.md)実行Office 365。

2. ディレクトリ同期が完了したら、組織のデバイスが Azure Windows 10参加ADしてください。 この手順は、デバイスごとに個別Windows 10されます。 詳細[については、「ユーザー WindowsデバイスをMicrosoft 365 Business Premiumする」](set-up-windows-devices.md)を参照してください。

3. デバイスが Azure Windows 10参加ADしたら、各ユーザーはデバイスを再起動し、ユーザーの資格情報を使用Microsoft 365 Business Premium必要があります。 これで、すべてのデバイスがオンプレミスのリソースにもアクセスできます。

Azure に参加しているデバイスのオンプレミス リソースにアクセスするには、追加AD必要ありません。 この機能は、Windows 10。

パスワード以外の AADJ デバイスにログインする予定がある場合 WHFB 資格情報ログインを介して PIN/Bio-metric のようにし、オンプレミスのリソース (共有、プリンターなど)[](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)にアクセスする場合は、この記事に従います。

組織が上記の Azure AD参加デバイス構成に展開する準備ができていない場合は、ハイブリッド Azure AD [参加デバイス構成のセットアップを検討してください](manage-windows-devices.md)。

### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Azure デバイスにデバイスをWindowsする際の考慮事項AD

Azure-Windows参加しているADが以前にドメインに参加しているか、ワークグループに参加している場合は、次の制限を考慮してください。

- デバイス Azure が参加AD、既存のプロファイルを参照せずに新しいユーザーを作成します。 プロファイルは手動で移行する必要があります。 ユーザー プロファイルには、お気に入り、ローカル ファイル、ブラウザー設定、およびユーザー設定スタート メニュー含まれる。 最適な方法は、既存のファイルと設定を新しいプロファイルにマップするサード パーティ製のツールを見つける方法です。

- デバイスがグループ ポリシー オブジェクト (GPO) を使用している場合、一部の GPO には Intune で同等の [構成](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) サービス プロバイダー (CSP) が含されていない場合があります。 [MMAT ツールを実行して](https://www.microsoft.com/download/details.aspx?id=45520)、既存の GPO に対応する CSP を検索します。

- ユーザーが Active Directory 認証に依存するアプリケーションに対して認証できない場合があります。 従来のアプリを評価し、可能であれば最新の Auth を使用するアプリへの更新を検討します。

- Active Directory プリンターの検出が機能しません。 すべてのユーザーに直接プリンター パスを指定するか、ユニバーサル 印刷 [を使用できます](/universal-print/)。

### <a name="related-articles"></a>関連記事

[Azure サーバーの前提条件AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
