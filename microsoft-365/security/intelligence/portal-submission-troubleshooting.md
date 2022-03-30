---
title: 管理者ブロックによって発生する MSI ポータルのエラーのトラブルシューティング
description: MSI ポータルのエラーのトラブルシューティング
ms.reviewer: ''
keywords: セキュリティ、サンプル提出ヘルプ、マルウェア ファイル、ウイルス ファイル、トロイの木馬ファイル、送信、Microsoft への送信、サンプルの提出、ウイルス、トロイの木馬、ワーム、検出されない、検出されない、電子メール microsoft、電子メール マルウェア、これはマルウェアだと思います、ウイルスを送信できるウイルス、これはウイルス、MSE、検出なし、署名なし、検出、疑わしいファイル、です。 MMPC、Microsoft マルウェア プロテクション センター、研究者、アナリスト、WDSI、セキュリティ インテリジェンス
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: e70eb5192a1fd6171b8e515509ad336aa99a2c63
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680357"
---
# <a name="troubleshooting-malware-submission-errors-caused-by-administrator-block"></a>管理者ブロックによるマルウェアの送信エラーのトラブルシューティング
場合によっては、感染している可能性のあるファイルを [分析のために Microsoft セキュリティ](https://www.microsoft.com/wdsi) インテリジェンス Web サイトに提出しようとするときに、管理者ブロックによって提出の問題が発生する場合があります。 次のプロセスは、この問題を解決する方法を示しています。

## <a name="review-your-settings"></a>設定の確認
Azure のアプリケーション設定[Enterprise開きます](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/UserSettings/menuId/)。 [**Enterprise ApplicationsUsers** >   は、自分の代わりに会社のデータにアクセスするアプリに同意できます。[はい] または [いいえ] が選択されているかどうかを確認します。

- **[いいえ]** が選択されている場合Azure ADテナントの管理者は、組織に同意する必要があります。 サーバーの構成によってはAzure AD、ユーザーは同じダイアログ ボックスから要求を送信できる場合があります。 管理者の同意を求めるオプションがない場合、ユーザーはこれらのアクセス許可を Azure AD 管理者に追加する必要があります。詳細については、次のセクションに移動します。

- [**はい**] が選択されている場合は、[セキュリティ インテリジェンス アプリWindows Defenderユーザーがサインインするために有効になっているか **?** が Azure で **[は** い] に [設定されている必要があります](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Properties/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/4a918a14-4069-4108-9b7d-76486212d75d)。[**いいえ]** が選択されている場合は、管理者が有効にするAzure ADする必要があります。 
  
## <a name="implement-required-enterprise-application-permissions"></a>必須のアプリケーションEnterpriseを実装する 
このプロセスには、テナントのグローバル管理者またはアプリケーション管理者が必要です。
 1. [アプリケーション[Enterprise開きます](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Permissions/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/4a918a14-4069-4108-9b7d-76486212d75d)。 
 2. [組織 **の管理者の同意を許可する] を選択します**。
 3. 実行できる場合は、次の図に示すように、このアプリケーションに必要な API アクセス許可を確認します。 テナントに同意を提供します。

    ![同意イメージを付与します。](../../media/security-intelligence-images/msi-grant-admin-consent.jpg)

  4. 管理者が手動で同意を提供しようとしてエラーを受け取った場合は、可能な限り、オプション [1](#option-1-approve-enterprise-application-permissions-by-user-request) または [オプション 2](#option-2-provide-admin-consent-by-authenticating-the-application-as-an-admin) を試してください。
  
## <a name="option-1-approve-enterprise-application-permissions-by-user-request"></a>オプション 1 ユーザー要求によるエンタープライズ アプリケーションのアクセス許可の承認
> [!Note]
> これは現在、プレビュー機能です。

Azure Active Directory管理者は、ユーザーがアプリに対する管理者の同意を要求できる必要があります。 アプリケーションで設定が **[は**[い] に構成Enterpriseします](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/UserSettings/menuId/)。

![Enterpriseユーザー設定を選択します。](../../media/security-intelligence-images/msi-enterprise-app-user-setting.jpg)

詳細については、「Configure [Admin consent workflow」を参照してください](/azure/active-directory/manage-apps/configure-admin-consent-workflow)。

この設定が確認された後、 [ユーザーは Microsoft](https://www.microsoft.com/wdsi/filesubmission) セキュリティ インテリジェンスでエンタープライズ顧客サインインを行い、正当性を含む管理者の同意を要求することができます。

![Contoso のサインイン フロー。](../../media/security-intelligence-images/msi-contoso-approval-required.png)

管理者は、アプリケーションのアクセス許可 Azure 管理者の同意要求を確認 [および承認できます](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/AccessRequests/menuId/)。

同意を得た後、テナント内のすべてのユーザーがアプリケーションを使用できます。
  
## <a name="option-2-provide-admin-consent-by-authenticating-the-application-as-an-admin"></a>オプション 2 アプリケーションを管理者として認証して管理者の同意を提供する 
このプロセスでは、グローバル管理者が Microsoft セキュリティ インテリジェンスEnterprise顧客サインイン フローを通過[する必要があります](https://www.microsoft.com/wdsi/filesubmission)。

![同意サインイン フロー。](../../media/security-intelligence-images/msi-microsoft-permission-required.jpg)

次に、管理者はアクセス許可を確認し、組織の代わりに **[同意**] を選択し、[同意する] を選択 **します**。

テナント内のすべてのユーザーが、このアプリケーションを使用できます。

## <a name="option-3-delete-and-readd-app-permissions"></a>オプション 3: アプリのアクセス許可を削除して読み取る
どちらのオプションでも問題が解決しない場合は、次の手順 (管理者として) を試してください。

1. アプリケーションの以前の構成を削除します。 [アプリケーションの [Enterprise] に移動し、[](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Properties/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/982e94b2-fea9-4d1f-9fca-318cda92f90b)削除] を **選択します**。

   ![アプリのアクセス許可を削除します。](../../media/security-intelligence-images/msi-properties.png)

2. プロパティから TenantID を [キャプチャします](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。

3. {tenant-id} を、以下の URL でこのアプリケーションに同意する必要がある特定のテナントに置き換えます。 この URL をブラウザーにコピーします。 残りのパラメーターは既に完了しています。 
``https://login.microsoftonline.com/{tenant-id}/v2.0/adminconsent?client_id=f0cf43e5-8a9b-451c-b2d5-7285c785684d&state=12345&redirect_uri=https%3a%2f%2fwww.microsoft.com%2fwdsi%2ffilesubmission&scope=openid+profile+email+offline_access``

   ![必要なアクセス許可。](../../media/security-intelligence-images/msi-microsoft-permission-requested-your-organization.png)

4. アプリケーションで必要なアクセス許可を確認し、[同意する] を **選択します**。 

5. アクセス許可が Azure portal に適用されるの [を確認します](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Permissions/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/ce60a464-5fca-4819-8423-bcb46796b051)。

   ![アクセス許可が適用されるのを確認します。](../../media/security-intelligence-images/msi-permissions.jpg)
   
6. 管理者以外の [アカウントを](https://www.microsoft.com/wdsi/filesubmission) 使用してエンタープライズ ユーザーとして Microsoft セキュリティ インテリジェンスにサインインして、アクセス権を持っている場合に確認します。

 これらのトラブルシューティング手順に従った後に警告が解決されない場合は、Microsoft サポートに問い合わせください。