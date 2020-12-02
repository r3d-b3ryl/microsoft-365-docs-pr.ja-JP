---
title: Microsoft クラウドの移行に関するその他の一般的な情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: 新しいドイツデータセンターリージョンの Microsoft Cloud ドイツ (Microsoft Cloud Deut上陸ランド) から Office 365 services に移行する際の、サービスに関するその他の一般的な情報。'
ms.openlocfilehash: 6fa09165f8aaa68e0f9fc567d96a4e53baaa594e
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551784"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft クラウドの移行に関するその他の一般的な情報

次のセクションでは、サービス、作業前の考慮事項、および顧客の操作に関する追加情報について説明します。

## <a name="azure-active-directory"></a>Azure Active Directory

Azure ドイツ cloud から Azure パブリッククラウドへの移行を完了するには、アプリケーション用の認証エンドポイント、Azure Active Directory (Azure AD) グラフ、および MS Graph エンドポイントを、OpenID Connect (OIDC) エンドポイントの報告を開始する際に商用クラウドのエンドポイントに更新することをお勧め `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` します。 
 
**いつこの変更を行う必要がありますか?**

テナントがドイツのクラウドから商用クラウドへの移行を完了すると、Azure/Office ポータルに通知が送信されます。 この通知を受信してから30日以内であれば、アプリは Azure ドイツ cloud から Azure パブリッククラウドに移行されるテナントに対して引き続き作業を行うことができます。
 
サインイン権限を更新するには、次の3つの前提条件があります。

 - テナントの OIDC discovery エンドポイントは、 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` AZURE AD パブリッククラウドエンドポイントを返します。

 - テナントがフェデレーション用にセットアップされている場合、Active Directory フェデレーションサービス (AD FS) は Azure AD パブリックと同期するように更新されます。 この変更を行うには、手順に従って Azure AD Connect 設定を更新します。

 - アプリケーションによって使用されるリソースアプリケーションは、Azure AD ドイツと Azure AD パブリックの両方によって署名されたトークンを受け付けるように変更されます。
 
**アプリケーションの種類**

アプリケーションには、次のいずれかを指定できます。

- シングルページアプリ (SPA)
- ユーザーにサインインする Web アプリ
- Web Api を呼び出す web アプリ
- 保護された web API
- Web api を呼び出す web API
- デスクトップ アプリ
- デーモンアプリ
- モバイル アプリ
 
> [!NOTE] 
> アプリケーションが権限としてを使用するように切り替えると `login.microsoftonline.com` 、この新しい権限によってトークンが署名されます。 他のアプリから呼び出されるリソースアプリケーションをホストしている場合は、有効なトークン検証を許可する必要があります。 これは、アプリが Azure AD ドイツと Azure AD パブリッククラウドの両方によって署名されたトークンを許可する必要があることを意味します。 この柔軟なトークン検証は、サービスを呼び出すすべてのクライアントアプリケーションが Azure AD パブリッククラウドに完全に移行されるまで必要です。 移行後、リソースアプリケーションは、Azure AD パブリッククラウドによって署名されたトークンのみを受け入れる必要があります。

**更新する必要があるもの**

1. Azure ドイツユーザーまたは Office 365 ドイツユーザーの認証に使用される Azure ドイツのアプリケーションをホストしている場合は、 `https://login.microsoftonline.com` が認証コンテキストの権限として使用されていることを確認してください。

    - 「Azure AD 認証コンテキスト」を参照してください。
    - これは、アプリケーションに対する認証に加えて、アプリケーションが呼び出している Api (Microsoft Graph、Azure AD Graph、Azure Resource Manager) に対する認証にも適用されます。

2. Azure AD Graph エンドポイントをに更新 `https://graph.windows.net` します。

3. MS Graph エンドポイントをに更新 `https://graph.microsoft.com` します。

4. アプリケーションによって使用されるドイツのクラウドエンドポイント (Exchange Online や SharePoint Online など) を、パブリッククラウドのものに更新します。

5. `AzurePublic` `AzureGermany` 次のための管理ツールおよびスクリプトで、環境パラメーター (ではなく) を更新します。

    - Azure PowerShell
    - Azure AD PowerShell (MSOnline)
    - Azure AD PowerShell (AzureAD)
    - Azure CLI
 
**公開するアプリケーションについて**

テナントの外部にいるユーザーが使用できるアプリケーションを公開する場合は、アプリケーションの登録を変更して継続性を確保する必要があります。 アプリケーションを使用する他のテナントは、テナントとは別の時間に移動する場合があります。 アプリケーションへのアクセスが失われないようにするには、Azure ドイツから Azure パブリックに同期するアプリに同意する必要があります。

### <a name="additional-considerations"></a>その他の考慮事項

Azure AD に関するその他の考慮事項を次に示します。

- フェデレーション認証の場合:

  - テナント遷移の処理中は、フェデレーションドメインの作成、昇格、または降格は行わないでください。 Azure AD サービスへの移行が完了したら (テナントは完全に完了)、フェデレーションドメインの管理を再開できます。

  - Active Directory フェデレーションサービス (AD FS) でフェデレーション認証を使用している場合は、移行中に社内の Active Directory ドメインサービス (AD DS) ですべての認証に使用される発行者 Uri を変更しないでください。 発行者 Uri を変更すると、ドメイン内のユーザーに対する認証エラーが発生します。 発行者 Uri は、AD FS で直接変更することも、ドメインを管理対象からフェデレーションに変換したり、その逆に変換したりすることもできます。 Microsoft では、移行される Azure AD テナント内のフェデレーションドメインを追加、削除、または変換しないことをお勧めします。 発行者 Uri は、移行が完全に完了した後で変更できます。

- ネットワークの場合:

  - IPv6 という名前のネットワークの作成は、Azure portal では機能しません `http://portal.microsoftazure.de/` 。 Azure portal をで使用して、 `https://portal.azure.com` IPv6 という名前のネットワークを作成します。
 
   - Azure 多要素認証 (MFA) サービス設定の信頼された IP アドレスの範囲は、Microsoft Cloud Deut/陸ポータルから作成することはできません。 Azure AD portal for Office 365 サービスを使用して、Azure MFA の信頼できる IP アドレスの範囲を作成します。


- 条件付きアクセスの場合: 

  - 次の付与コントロールを持つ条件付きアクセスポリシーは、Office 365 サービスへの移行が完了するまでサポートされません ( [Finalize AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration フェーズの後)。

    - 準拠デバイスが必要
    - 承認済みアプリの要求
    - アプリ保護ポリシーが必要
    
  - 条件付きアクセスポリシーインターフェイスでは、テナントに対して有効になっているセキュリティの既定については、無効になっていても、テナントに対して既に条件付きアクセスポリシーが存在することについて警告が表示されます。 この警告を無視するか、Office 365 services ポータルを使用して条件付きアクセスポリシーを管理する必要があります。 

- Intune シナリオは、すべての office ワークロードの移行を含む、テナントの移行が完了した後の全世界のエンドポイントに対してのみサポートされます。

- Microsoft Cloud Deutmfa 要求に対してモバイルアプリ通知方法を使用するユーザーには、Microsoft Authenticator アプリのユーザープリンシパル名 (UPN) ではなく、ユーザーの ObjectId (GUID) が表示されます。 Azure AD テナントの移行が完了し、Office 365 サービスでホストされると、新しい Microsoft Authenticator ライセンス認証によってユーザーの Upn が表示されます。 既存の Microsoft Authenticator アカウントでは、引き続き user ObjectId が表示されますが、モバイルアプリの通知には引き続き機能します。 

- 2019年10月22日以降に作成されたテナントの場合、セキュリティの既定値は、Office 365 サービスに移行すると、テナントに対して自動的に有効になります。 テナント管理者は、セキュリティの既定値を有効のままにして MFA を登録することも、機能を無効にすることもできます。 詳細については、「 [セキュリティの既定値を無効](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)にする」を参照してください。 

  > [!NOTE]
  > 移行中に自動では有効になっていない組織は、Office 365 サービスでセキュリティの既定値を有効にする機能として今後自動的に登録されることがあります。 セキュリティの既定値を明示的に無効にするか有効にするかどうかを選択する管理者は、 **Azure Active Directory > のプロパティ** で機能を更新します。 この機能が管理者によって明示的に有効にされた後は、自動では有効になりません。

- テナントが移行されると、office 365 ドイツポータルだけでなく、office 365 ポータルにも Azure AD Connect のバージョンに関する警告が表示されます。 バージョン警告で移行が完了した後に警告が表示されなくなった場合は、この設定を無視できます。 移行前または移行後に警告が発生した場合は、どちらのポータルでも Azure AD Connect を更新する必要があります。 "古いディレクトリ同期ツールを使用しています" という警告メッセージが表示されます。 最新バージョンの Azure AD Connect を入手するには、Microsoft ダウンロードセンターにアクセスすることをお勧めします。

## <a name="exchange-online"></a>Exchange Online 

- `myaccount.msft.com` は、Office 365 をカットオーバーした後にのみ機能します。 リンクによって "問題が発生しました" というエラーメッセージが表示されます。

- 他の環境の共有メールボックスにアクセスする Outlook Web App のユーザー (たとえば、ドイツ環境のユーザーがグローバル環境の共有メールボックスにアクセスする)、2回目の認証を求めるメッセージが表示されます。 ユーザーは、で自分のメールボックスを認証してアクセスし、 `outlook.office.de` にある共有メールボックスを開く必要があり `outlook.office365.com` ます。 他のサービスでホストされている共有リソースにアクセスするときは、2回目の認証が必要になります。

- 既存の Microsoft Cloud Deut上陸お客様、または移行されたメールボックスの場合、[ファイル >] [Info] を使用して Outlook に共有メールボックスを追加すると **> アカウントの追加** は失敗する可能性があります (outlook クライアントが Rest API を使用しようとして `https://outlook.office.de/api/v2.0/Me/Calendars` います)。予定表のアクセス許可を表示するためのアカウントを追加する場合は、「 [Outlook で予定表を共有するためのユーザー操作の変更](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 」で説明されているようにレジストリキーを追加して、この操作が正常に行われるようにすることができます。 このレジストリキーは、グループポリシーを使用して組織全体に展開することができます。

- 移行フェーズでは、PowerShell コマンドレット **new-migrationendpoint**、 **New-migrationendpoint**、および **MigrationsServerAvailability** を使用すると、エラーが発生する場合があります (プロキシでのエラー)。 これは、調停メールボックスが世界中に移行されたが、管理メールボックスが存在しないか逆の場合に発生します。 このエラーを解決するには、テナントの PowerShell セッションを作成している間に、 **Connectionuri** のルーティングヒントとして調停メールボックスを使用します。 例: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Exchange Online ハイブリッドを使用している場合:

    - ハイブリッド構成ウィザード (HCW) を再実行して、移行の前に Microsoft Cloud Deut上陸陸に対してオンプレミスの構成を更新し、Office 365 サービスに対してクリーンアップ時に HCW を再実行する必要があります。 カスタムドメインを使用する場合は、追加の DNS 更新が必要になることがあります。

このワークロードの移行フェーズ中に必要な操作、または管理または使用に対する影響の詳細については、「 [移行フェーズの操作と影響](ms-cloud-germany-transition-phases.md#exchange-online)」の「Exchange Online」のセクションを参照してください。

## <a name="office-services"></a>Office サービス

Office の最近使用した (MRU) サービスは、ドイツサービスから Office 365 サービスへのカットオーバーであり、移行ではありません。 Office.com ポータルから移行した後は、Office 365 services 側の MRU リンクのみが表示されます。 ドイツのサービスからの MRU リンクは、Office 365 サービスで MRU リンクとして表示されません。 Office 365 では、MRU リンクは、テナントの移行が完了した後にのみアクセスできます。

## <a name="sharepoint-online-and-onedrive"></a>SharePoint Online と OneDrive

- ドイツ リージョンへの SharePoint Online の移行が完了すると、データ インデックスが再構築されます。 インデックスの再作成が完了している間は、検索インデックスに依存する機能が影響を受ける可能性があります。

- 組織が SharePoint 2010 ワークフローを引き続き使用している場合は、2021年12月31日以降、機能しなくなります。 SharePoint 2013 のワークフローは引き続きサポートされますが、既定では、2020年11月1日から始まる新しいテナントに対して無効になっています。 SharePoint Online サービスへの移行が完了したら、パワー自動化または他のサポートされているソリューションに移行することをお勧めします。

- ドイツ地域への OneDrive の移行が完了したら、データインデックスが再構築されます。 インデックスの再作成が進行中の場合、検索インデックスに依存する機能が影響を受ける可能性があります。


## <a name="more-information"></a>詳細情報

はじめに:

- [新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中の顧客の利便性](ms-cloud-germany-transition-experience.md)

遷移を移動します。

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の準備作業](ms-cloud-germany-transition-add-pre-work.md)
- [サービス](ms-cloud-germany-transition-add-general.md)、[デバイス](ms-cloud-germany-transition-add-devices.md)、[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、 [AD FS](ms-cloud-germany-transition-add-adfs.md)の追加情報。

クラウドアプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
