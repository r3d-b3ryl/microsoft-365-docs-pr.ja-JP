---
title: Microsoft Cloud Deutschland からの移行に関するその他のデバイス情報
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
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツのデータセンター地域の Office 365サービスに移行する場合のサービスに関するその他のデバイス情報。'
ms.openlocfilehash: 1eb7b18360cefeeb2d5770c3d77e564d5a757a5e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453569"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行に関するその他のデバイス情報

Azure AD、Microsoft Cloud Deutschland に接続されている登録済みデバイスは、フェーズ 9 以降およびフェーズ 10 より前に移行する必要があります。 デバイスの移行は、デバイスの種類、オペレーティング システム、および Azure のADされます。

## <a name="azure-ad-joined-windows-10-devices"></a>Azure AD参加Windows 10デバイス
デバイスが Azure Windows 10参加しているAD、Azure デバイスから切断され、再び接続AD必要があります。

[![Azure AD デバイス Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


ユーザーが Windows 10 デバイスの管理者である場合、ユーザーは Azure AD からデバイスの登録を解除し、3 つの手順で再度参加できます。

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>手順 1: デバイスが Azure ID に参加しているかどうかを判断する

1. 職場アカウントでサインインします。
2. [アカウントアクセス設定  >    >  **ワークまたは学校] に移動します**。
3. **[...]' に接続されているアカウントを一覧で探します。s Azure AD**.
4. 接続されているアカウントが存在する場合は、手順 2 に進みます。

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>手順 2: Azure サーバーからデバイスを切断AD

1. 接続されている **作業時間または** 学校アカウントで [切断] をクリックします。
2. 切断を 2 回確認します。
3. ローカル管理者のユーザー名とパスワードを入力します。 デバイスが切断されています。
4. デバイスを再起動します。

### <a name="step-3-join-the-device-to-azure-ad"></a>手順 3: デバイスを Azure デバイスに参加AD

1. ローカル管理者の資格情報を使用してサインインします。
2. [アカウントアクセス設定  >    >  **ワークまたは学校] に移動します**。
3. **[接続]** をクリックします。
4. **重要**: **[Azure に参加] をクリックAD。**
5. 仕事用アカウントの電子メール アドレスとパスワードを入力します。 デバイスが接続されています。
6. デバイスを再起動します。
7. 仕事用アカウントのメール アドレスとパスワードでサインインします。

ユーザーがデバイスの管理者ではない場合、Azure AD グローバル管理者は、この構成パスに従ってデバイスにローカル管理者アカウントを作成し、デバイスに接続を解除できます。

*設定 > アカウント > アカウント >資格情報不明 > Microsoft-Account を使用せずにユーザーを追加する*

再参加の場合、組織の任意の作業アカウントの資格情報をこの手順で使用できます。

デバイスに参加するために使用される作業アカウントは、デバイスの管理者として自動的に昇格されます。
組織の他の仕事用アカウントはデバイスにサインインできますが、管理者権限はありません。

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a>Azure ADデバイスに登録された (workplace-joined) Windows 10デバイス

デバイスが azure Windows 10登録されているAD場合は、Azure デバイスから切断され、再度接続AD必要があります。

[![Azure AD デバイス Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a>手順 1: デバイスが Azure ID 登録かどうかを判断する

1. ユーザーと一緒にサインインします。
2. [アカウントアクセス設定  >    >  **ワークまたは学校] に移動します**。
3. 一覧で作業用アカウントを検出し **、[....]に接続されていることを確認します。s Azure AD**.

    仕事用アカウントが一覧にあるのに Azure サーバーに接続されていない場合AD手順 2 に進みます。

    それ以外の場合、デバイスは Azure AD参加しているデバイスであり、Azure AD参加デバイスWindows 10[必要があります](#azure-ad-joined-windows-10-devices)。

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>手順 2: Azure サーバーからデバイスを切断AD

1. 仕事用アカウントをクリックします。 [情報] ボタン *と [切断* ] *ボタンが* 表示されます。
2. [切断 **] をクリックします**。
3. [はい] をクリックして、デバイスからのアカウントの削除を **確認します**。

### <a name="step-3-connect-the-device-to-azure-ad"></a>手順 3: Connect Azure デバイスに接続AD

1. **[接続]** をクリックします。
2. 仕事用アカウントのメール アドレスを入力し、[次へ] を **クリックします**。
3. 仕事用アカウントのパスワードを入力し、[サインイン] **をクリックします**。
4. [完了] をクリックして **確認します**。 作業アカウントが再び表示されます。

## <a name="android"></a>Android

Android の場合、ユーザーはデバイスの登録を解除して再登録する必要があります。 これは、アプリまたはアプリMicrosoft Authenticator使用してポータル サイトできます。

- アプリからMicrosoft Authenticatorデバイス登録に移動設定 >**できます**。 そこから、ユーザーはデバイスの登録を解除して再登録できます。

- [デバイス] ポータル サイト[デバイス]**タブに** 移動し、デバイスを削除できます。 その後、デバイスを使用してデバイスを再登録ポータル サイト。

- ユーザーは、アカウント設定ページからアカウントを削除してから、作業アカウントを再追加することで、登録を解除して再登録することもできます。

Android アプリを使用してデバイスの登録を解除して再登録するには、次Microsoft Authenticatorします。

1. アプリを開Microsoft Authenticatorに移動し、[設定]**に移動します**。
2. [デバイス **登録] を選択します**。
3. [登録解除] を選択してデバイスの登録を **解除します**。
4. [ **デバイスの登録]** で、電子メール アドレスを入力してデバイスを再登録し、[登録] を **選択します**。

Android デバイスの登録を解除して、Android デバイスを再登録するには、次設定します。

1. [デバイス **] ウィンドウ設定** 開き、[アカウント] に **移動します**。
2. 再登録する作業アカウントを選択し、[アカウントの削除] **を選択します**。
3. アカウントを削除した後、[アカウント] ページ **で** 、[アカウントの追加] **を選択し、[>] を選択します**。
4. [Workplace **Join] で**、電子メール アドレスを入力し、[参加] を **選択** してデバイスの登録を完了します。

Android でデバイスの登録を解除して再登録するには、次ポータル サイト。

1. [デバイスポータル サイト起動し、[デバイス] タブ **に移動** します。
2. デバイスを選択すると、デバイスの詳細が表示されます。
3. 省略記号 (3 つのドット)メニューから [デバイスの削除] を選択し、ダイアログで確認して削除を完了します。
4. これで、アプリからログアウトポータル サイトがあります。 [ **サインイン] を選択** してデバイスを再登録します。

このワークロードの移行フェーズ中に必要なアクション、または管理または使用状況への影響の詳細については[、「Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)からの移行に関する Azure AD の追加情報」の「Azure Active Directory (Azure AD) に関する情報」を参照してください。

## <a name="ios"></a>iOS

iOS デバイスでは、ユーザーはキャッシュされたアカウントを Microsoft Authenticator から手動で削除し、デバイスの登録を解除し、デバイス上のネイティブ アプリからサインアウトする必要があります。

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>手順 1: 存在する場合は、アプリからアカウントMicrosoft Authenticatorします。

1. アプリでアカウントをタップMicrosoft Authenticatorします。
2. 右上隅にある **設定** アイコンをタップします。 このアイコンが表示 **されない設定、** 最新バージョンのファイルを使用していない可能性Microsoft Authenticator。
3. [アカウントの **削除] ボタンをタップ** します。
4. [この **デバイスのすべてのアプリ] をタップします**。

### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>手順 2: アプリからデバイスの登録をMicrosoft Authenticatorする

1. 右上隅にあるメニュー アイコンをタップします。
2. [デバイス **設定]** をタップし、[デバイス **登録] をタップします**。
3. アカウントが表示されている場合は、[デバイスの登録を **解除] をタップ** し、ダイアログで [ **続行** ] をタップします。 その後、アカウントが表示されません。

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>手順 3: 必要に応じて、個々のアプリからサインアウトする

ユーザーは、個々のアプリ (Outlook、Teams、OneDrive、それらのアプリからアカウントを削除できます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**組織が影響を受けるかを確認する方法を教えてください。**

管理者は、Azure アカウントが登録済みか `https://portal.microsoftazure.de` 、または Azure AD参加AD確認する必要があります。 組織に Azure ADまたは Azure AD参加している場合、組織は、このページの指示に従う必要があります。

**ユーザーがデバイスを再登録する場合**

フェーズ [9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) の完了後にデバイスの登録を解除して再登録する必要がある場合は、成功にとって重要です。 フェーズ 10 が開始する前に再登録を完了する必要があります。それ以外の場合は、デバイスへのアクセスが失われる可能性があります。

**すべてのデバイスがパブリック クラウドに登録されているのを知る方法**

デバイスがパブリック クラウドに登録されているかどうかを確認するには、Azure AD ポータルからデバイスのリストをエクスポートして、Excelする必要があります。 次に、組織が移行プロセスのフェーズ 9 を通過した日付の後に 、登録されているデバイスを _(registeredTime_ 列を使用して) [フィルター処理します](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)。

**「Microsoft の DNS レコードを作成する」に記載されている DNS 名を追加する必要がある場合は、Windows [ベースの DNS を使用しますか](/microsoft-365/admin/dns/create-dns-records-using-windows-based-dns?view=o365-worldwide#add-two-cname-records-for-mobile-device-management-mdm-for-microsoft)。**

この DNS エントリは、デバイスの再登録には不要です。 

## <a name="additional-considerations"></a>その他の考慮事項

> [!IMPORTANT]
> Intune サービス プリンシパルは、移行プロセスのフェーズ [3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)の後に有効になります。これは、デバイス登録に対する Azure ADを意味します。 移行前に Azure AD デバイス登録をブロックした場合は、PowerShell を使用して Intune サービス プリンシパルを無効にして、Azure AD デバイス登録を Azure AD ポータルで再度無効にする必要があります。 このコマンドを使用して Intune サービス プリンシパルを無効にAzure Active Directory PowerShell Graphできます。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a>詳細情報

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

切り替えの移動:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の作業前](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移行プログラム情報](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams へのアップグレードを開始する](/microsoftteams/upgrade-start-here)
