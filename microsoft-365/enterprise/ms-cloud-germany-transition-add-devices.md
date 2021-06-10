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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861308"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行に関するその他のデバイス情報

Azure AD、Microsoft Cloud Deutschland に接続されている登録済みデバイスは、フェーズ 9 以降およびフェーズ 10 より前に移行する必要があります。 デバイスの移行は、デバイスの種類、オペレーティング システム、および AAD の関係によって異なります。 

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**組織が影響を受けるかを確認する方法を教えてください。**

管理者は、登録済みデバイスまたは Azure デバイスが参加しているデバイスAD `https://portal.microsoftazure.de` 確認する必要があります。 組織にデバイスが登録されている場合は、影響を受ける可能性があります。

**ユーザーに与える影響は何ですか?**

移行フェーズ [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) が完了し、Microsoft Cloud Deutschland のエンドポイントが無効になった後、登録済みデバイスのユーザーはサインインできなくなります。  

組織が Microsoft Cloud Deutschland から切断される前に、すべてのデバイスがワールドワイド エンドポイントに登録されている必要があります。
  
**ユーザーがデバイスを再登録する場合**

フェーズ [9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) の完了後にデバイスの登録を解除して再登録する必要がある場合は、成功にとって重要です。 フェーズ 10 が開始する前に再登録を完了する必要があります。それ以外の場合は、デバイスへのアクセスが失われる可能性があります。

**移行後にデバイスの状態を復元する方法**

Azure AD に登録されている会社所有の Windows デバイスの場合、管理者は、古いデバイスの状態を登録解除するリモートでトリガーされたワークフローを通じて、これらのデバイスの移行を管理できます。
  
Azure Windowsに登録されている個人用デバイスADを含む他のすべてのデバイスでは、これらの手順を手動で実行する必要があります。 Azure AD参加しているデバイスの場合、ユーザーはデバイスの登録を解除してから再登録するローカル管理者アカウントを持っている必要があります。

デバイスの状態を正常に復元する方法については、以下の詳細な手順を参照してください。 
 
**すべてのデバイスがパブリック クラウドに登録されているのを知る方法**

デバイスがパブリック クラウドに登録されているかどうかを確認するには、Azure AD ポータルからデバイスのリストをエクスポートして、Excelする必要があります。 次に [、Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized)移行フェーズから分離した後、登録されているデバイスを _(registeredTime_ 列を使用して) フィルター処理します。

## <a name="additional-considerations"></a>その他の考慮事項
デバイスの登録は、テナントの移行後に非アクティブ化され、有効または無効にすることはできません。 

Intune を使用しない場合は、サブスクリプションにサインインし、このコマンドを実行してオプションを再アクティブ化します。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
**重要:** Intune サービス プリンシパルは、コマースの移行後に有効になります。これは、デバイス登録に対する Azure ADを意味します。 移行前に Azure AD デバイス登録をブロックした場合は、PowerShell を使用して Intune サービス プリンシパルを無効にして、Azure AD デバイス登録を Azure AD ポータルで再度無効にする必要があります。 このコマンドを使用して Intune サービス プリンシパルを無効にAzure Active Directory PowerShell Graphできます。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a>Azure AD参加
これは、デバイスのWindows 10適用されます。 

デバイスが Azure デバイスに参加AD場合は、Azure サーバーから切断され、AD接続されている必要があります。 

[![Azure AD デバイス Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


ユーザーがデバイスの管理者であるWindows 10、ユーザーは Azure デバイスからデバイスの登録を解除し、AD再度参加できます。 管理者特権がない場合、ユーザーは、このコンピューター上のローカル管理者アカウントの資格情報を必要とします。 


管理者は、次の構成パスに従ってデバイスにローカル管理者アカウントを作成できます。

*設定 > アカウント > アカウント >資格情報不明 > Microsoft-Account を使用せずにユーザーを追加する*

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>手順 1: デバイスが Azure ID に参加しているかどうかを判断する
1.  ユーザーの電子メールとパスワードでサインインします。
2.  [アカウント] 設定 >[>] に移動します。 
3.  ..に接続されているリスト内 **のユーザーを探します。's Azure AD**. 
4.  接続されているユーザーが存在する場合は、手順 2 に進みます。 それがない場合は、それ以上の操作は必要ありません。
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>手順 2: Azure サーバーからデバイスを切断AD
1.  接続されている **作業時間** または学校アカウントで [切断] をタップします。 
2.  切断を 2 回確認します。 
3.  ローカル管理者のユーザー名とパスワードを入力します。 デバイスが切断されています。
4.  デバイスを再起動します。
### <a name="step-3-join-the-device-to-azure-ad"></a>手順 3: デバイスを Azure デバイスに参加AD
1.  ユーザーがローカル管理者の資格情報でサインインする
2.  [アカウント]**設定[仕事または** 学校に **アクセスする] の順に移動します。** 
3.  **[Connect**
4.  **重要**: **[Azure に参加] をタップAD**
5.  ユーザーの電子メール アドレスとパスワードを入力します。 デバイスが接続されている
6.  デバイスを再起動する 
7.  電子メール アドレスとパスワードで署名する

## <a name="azure-ad-registered-company-owned"></a>Azure AD登録済み (会社所有)

デバイスが Azure Windows 10登録されているかどうかをADするには、デバイスで次のコマンドを実行します。

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

デバイスが Azure AD登録済みである場合は、次の出力が表示されます。

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

デバイス上の既存の Azure ADアカウントを削除するには、次の方法を実行します。

- デバイス上の Azure AD登録済みアカウントを削除するには、ここからダウンロードできるツールである CleanupWPJ [ を使用 ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)CleanupWPJ.zip。

- ZIP ファイルを抽出し **、WPJCleanup.cmd を実行します**。 このツールは、デバイス上のファイルのバージョンに基づいてWindows実行ファイルを起動します。

- グループ ポリシーのようなメカニズムを使用すると、管理者はデバイスにサインインしているすべてのユーザーのコンテキストで、デバイスでコマンドを実行できます。

Azure アカウント にデバイスを登録するように求める Web アカウント マネージャーのプロンプトを無効にするにはAD、次のレジストリ値を追加します。 

- 場所: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- 種類: DWORD (32 ビット)
- 名前: BlockAADWorkplaceJoin
- 値データ: 1

このレジストリ値が存在する場合は、職場への参加をブロックし、ユーザーにデバイスへの参加を求めるプロンプトが表示されるのを防ぐ必要があります。

## <a name="android"></a>Android

Android の場合、ユーザーはデバイスの登録を解除して再登録する必要があります。 これは、アプリまたはアプリMicrosoft Authenticator使用してポータル サイトできます。 

- アプリからMicrosoft Authenticatorデバイス登録に移動設定 >**できます**。 そこから、ユーザーはデバイスの登録を解除して再登録できます。
 
- [デバイス] ポータル サイト[デバイス]**タブに** 移動し、デバイスを削除できます。 その後、デバイスを使用してデバイスを再登録ポータル サイト。
 
- ユーザーは、アカウント設定ページからアカウントを削除してから、作業アカウントを再追加することで、登録を解除して再登録することもできます。

Android アプリを使用してデバイスの登録を解除して再登録するには、次Microsoft Authenticatorします。

1.  アプリを開Microsoft Authenticatorに移動し、[設定]**に移動します**。
2.  [デバイス **登録] を選択します**。
3.  [登録解除] を選択してデバイスの登録を **解除します**。
4.  [ **デバイスの登録]** で、電子メール アドレスを入力してデバイスを再登録し、[登録] を **選択します**。

Android デバイスの登録を解除して、Android デバイスを再登録するには、次設定します。

1.  [デバイス **] ウィンドウ設定** 開き、[アカウント] に **移動します**。
2.  再登録する作業アカウントを選択し、[アカウントの削除] **を選択します**。
3.  アカウントを削除した後、[アカウント] ページ **で** 、[アカウントの追加] **を選択し、[>] を選択します**。
4.  [Workplace **Join] で**、電子メール アドレスを入力し、[参加] を **選択** してデバイスの登録を完了します。

Android でデバイスの登録を解除して再登録するには、次ポータル サイト。

1.  [デバイスポータル サイト起動し、[デバイス] タブ **に移動** します。
2.  デバイスを選択すると、デバイスの詳細が表示されます。
3.  省略記号 (3 つのドット)メニューから [デバイスの削除] を選択し、ダイアログで確認して削除を完了します。
4.  これで、アプリからログアウトポータル サイトがあります。 [ **サインイン] を選択** してデバイスを再登録します。

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
4. アカウントが表示されている場合は、[デバイスの登録を **解除] をタップ** し、ダイアログで [ **続行** ] をタップします。 その後、アカウントが表示されません。
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>手順 3: 必要に応じて、個々のアプリからサインアウトする

ユーザーは、個々のアプリ (Outlook、Teams、OneDrive、それらのアプリからアカウントを削除できます。

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