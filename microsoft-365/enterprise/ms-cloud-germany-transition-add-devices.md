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
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター リージョンの Office 365 サービスに移行する場合のサービスに関するその他のデバイス情報。'
ms.openlocfilehash: 151fcac882dc91d96df3ece000c28d1a7abe1d1f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780298"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行に関するその他のデバイス情報

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**組織が影響を受けるのを確認する方法**

管理者は、デバイス `https://portal.microsoftazure.de` が登録されていないかどうかを確認する必要があります。 組織にデバイスが登録されている場合は、影響を受ける可能性があります。

**ユーザーにどのような影響がありますか?**

登録されたデバイスのユーザーは、移行が Azure 移行フェーズの最終段階に入った後 [AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) でサインインできなくなりました。  

組織が Microsoft Cloud Deutschland から切断される前に、すべてのデバイスがワールドワイド エンドポイントに登録されている必要があります。
  
**ユーザーがデバイスを再登録する場合**

成功するには [、Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) 移行フェーズとは別にデバイスの登録を解除して再登録する必要があります。

**移行後にデバイスの状態を復元する方法**

Azure AD に登録されているハイブリッド Azure AD に参加し、会社が所有する Windows デバイスが Azure AD に登録されている場合、管理者は、古いデバイスの状態の登録を解除するリモートでトリガーされたワークフローを通じて、これらのデバイスの移行を管理できます。
  
Azure AD に登録されている個人用 Windows デバイスを含む他のすべてのデバイスでは、エンド ユーザーは手動でこれらの手順を実行する必要があります。 Azure ADに参加しているデバイスの場合、ユーザーはデバイスの登録を解除してから再登録するためにローカル管理者アカウントを持っている必要があります。

Microsoft は、デバイスの状態を正常に復元する方法に関する手順を公開します。 
 
**すべてのデバイスがパブリック クラウドに登録されているのを確認する方法**

デバイスがパブリック クラウドに登録されているかどうかを確認するには、Azure AD ポータルから Excel スプレッドシートにデバイスの一覧をエクスポートしてダウンロードする必要があります。 次に [、Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized)移行フェーズから分離した後、登録されているデバイスを _(registeredTime_ 列を使用して) フィルター処理します。

デバイスの登録は、テナントの移行後に非アクティブ化され、有効または無効にすることはできません。 Intune が使用されていない場合は、サブスクリプションにサインインし、次のコマンドを実行してオプションを再アクティブ化します。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a>Hybrid Azure AD 参加

### <a name="windows-down-level"></a>Windows のダウンレベル

_Windows_ ダウンレベル デバイスは、現在、以前のバージョンの Windows (Windows 8.1 や Windows 7 など) を実行している、または 2019 および 2016 より前のバージョンの Windows Server を実行している Windows デバイスです。 このようなデバイスが以前に登録されている場合は、それらのデバイスの登録を解除して再登録する必要があります。 

Windows のダウンレベル デバイスが以前に Azure AD に参加したかどうかを確認するには、デバイスで次のコマンドを使用します。

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

デバイスが以前に Azure AD に参加し、デバイスがグローバル Azure AD エンドポイントへのネットワーク接続を持つ場合は、次の出力が表示されます。

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

影響を受けるデバイスは、値が "Unknown" の "Device state" になります。 出力が "デバイスに参加していない" 場合、または "デバイスの状態" の値が "Okay" の場合は、次のガイダンスは無視してください。

デバイスが参加している (deviceId、拇印などによって) "Device state" の値が "Unknown" であるデバイスに対してだけ、管理者はこのようなダウンレベル デバイスにサインインするドメイン ユーザーのコンテキストで次のコマンドを実行する必要があります。

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

上のコマンドは、Windows のダウンレベル デバイスにサインインするドメイン ユーザーごとに 1 回だけ実行する必要があります。 このコマンドは、ドメイン ユーザーのサインインのコンテキストで実行する必要があります。 

ユーザーが後でサインインするときに、このコマンドを実行しない場合は十分な注意が必要です。 前のコマンドを実行すると、サインインしたユーザーのローカル ハイブリッド Azure ADに参加しているコンピューターの参加状態がクリアされます。 また、コンピューターが引き続きハイブリッド Azure AD に参加するように構成されている場合は、ユーザーが再びサインインするときに参加を試みます。

### <a name="windows-current"></a>Windows Current

#### <a name="unjoin"></a>Unjoin

Windows 10 デバイスが以前に Azure AD に参加したかどうかを確認するには、デバイスで次のコマンドを実行します。

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

デバイスがハイブリッド Azure AD参加している場合、管理者には次の出力が表示されます。

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

出力が "AzureAdJoined : No" の場合は、次のガイダンスは無視してください。

デバイスが Azure AD に参加しているデバイスの場合にのみ、管理者として次のコマンドを実行して、デバイスの参加状態を削除します。

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

上のコマンドは、Windows デバイスの管理コンテキストで 1 回だけ実行する必要があります。

#### <a name="hybrid-ad-joinre-registration"></a>ハイブリッド AD Join\Re-Registration

デバイスは、グローバル Azure AD エンドポイントへのネットワーク接続がある限り、ユーザーまたは管理者の介入なしに自動的に Azure AD に参加します。 


## <a name="azure-ad-join"></a>Azure AD Join

**重要:** Intune サービス プリンシパルは、商取引の移行後に有効になります。これは、Azure AD Device Registration のアクティブ化を意味します。 移行前に Azure AD デバイス登録をブロックした場合は、PowerShell で Intune サービス プリンシパルを無効にして、Azure AD ポータルでの Azure AD デバイス登録を再度無効にする必要があります。 Azure Active Directory PowerShell for Graph モジュールで次のコマンドを使用して、Intune サービス プリンシパルを無効にできます。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Unjoin

Windows 10 デバイスが以前に Azure AD に参加したかどうかを確認するために、ユーザーまたは管理者はデバイスで次のコマンドを実行できます。

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

デバイスが Azure AD に参加している場合、ユーザーまたは管理者には次の出力が表示されます。

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

出力が "AzureAdJoined : NO" の場合は、次のガイダンスは無視してください。

ユーザー: デバイスが Azure AD参加している場合、ユーザーは設定からデバイスの参加を解除できます。 Azure AD からデバイスに接続を解除する前に、デバイスにローカル管理者アカウントが存在AD。 ローカル管理者アカウントは、デバイスにサインインし戻す必要があります。

管理者: 組織の管理者が、Azure AD に参加しているユーザーのデバイスの参加を解除する場合は、グループ ポリシーなどのメカニズムを使用して、各デバイスで次のコマンドを実行します。 管理者は、Azure アカウントからデバイスに接続を解除する前に、デバイスにローカル管理者アカウントが存在AD。 ローカル管理者アカウントは、デバイスにサインインし戻す必要があります。

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

上のコマンドは、Windows デバイスの管理コンテキストで 1 回だけ実行する必要があります。 

### <a name="azure-ad-joinre-registration"></a>Azure ADの参加/再登録

ユーザーは、Windows の設定からデバイスを Azure AD に参加>アカウント **>、> Connect** にアクセスします。
 

## <a name="azure-ad-registered-company-owned"></a>Azure AD登録済み (会社所有)

Windows 10 デバイスが Azure AD登録されているかどうかを確認するには、デバイスで次のコマンドを実行します。

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

デバイスが Azure AD Registered である場合、次の出力が表示されます。

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

デバイス上の既存の Azure AD登録済みアカウントを削除するには、次の方法を実行します。

- デバイスで Azure AD登録済みアカウントを削除するには、CleanupWPJ を使用します。このツールは、次の場所からダウンロード[CleanupWPJ.zip。 ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)

- ZIP ファイルを抽出し **、WPJCleanup.cmd を実行します**。 このツールは、デバイス上の Windows のバージョンに基づいて適切な実行可能ファイルを起動します。

- 管理者は、グループ ポリシーのようなメカニズムを使用して、デバイスにサインインしているすべてのユーザーのコンテキストで、デバイスでコマンドを実行できます。

Azure AD にデバイスを登録するように求める Web アカウント マネージャーのプロンプトを無効にするには、次のレジストリ値を追加します。 

- 場所: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- 型: DWORD (32 ビット)
- 名前: BlockAADWorkplaceJoin
- 値データ: 1

このレジストリ値が存在する場合は、職場への参加をブロックし、ユーザーにデバイスへの参加を求めるメッセージが表示されるのを防ぐ必要があります。

## <a name="android"></a>Android

Android の場合、ユーザーはデバイスの登録を解除して再登録する必要があります。 これは、Microsoft Authenticator アプリまたはポータル サイト アプリから実行できます。 

- Microsoft Authenticator アプリから、[デバイス登録] の [設定 **] >移動できます**。 そこから、ユーザーはデバイスの登録を解除して再登録できます。
 
- ポータル サイトから、[デバイス] タブに移動し、デバイスを削除できます。 その後、ポータル サイトを使用してデバイスを再登録します。
 
- ユーザーは、アカウント設定ページからアカウントを削除してから、仕事用アカウントを再追加することで、登録を解除して再登録することもできます。

Microsoft Authenticator アプリを使用して Android のデバイスの登録を解除して再登録するには、次の方法を使用します。

1.  Microsoft Authenticator アプリを開き、[設定] に移動 **します**。
2.  [デバイス **の登録] を選択します**。
3.  [登録解除] を選択してデバイスの登録を **解除します**。
4.  デバイス **登録の場合** は、電子メール アドレスを入力してデバイスを再登録し、[登録] を選択 **します**。

Android デバイスの登録を解除し、Android デバイスを [設定] ページに再登録するには、次の方法を使用します。

1.  デバイス設定 **を開き、[** アカウント] に **移動します**。
2.  再登録する仕事用アカウントを選択し、[アカウントの削除] **を選択します**。
3.  アカウントを削除した後、[アカウント]ページで[アカウントの追加] を選択し、[>**アカウント] を選択します**。
4.  Workplace **Join の場合は**、メール アドレスを入力し、[参加] **を選択して** デバイスの登録を完了します。

ポータル サイトから Android のデバイスの登録を解除して再登録するには、次の方法を実行します。

1.  ポータル サイトを起動し、[デバイス] タブ **に移動** します。
2.  デバイスを選択して、デバイスの詳細を表示します。
3.  省略記号 (3 つのドット)メニューから [デバイスの削除] を選択し、ダイアログで確認して削除を完了します。
4.  ポータル サイト アプリからログアウトする必要があります。 [ **サインイン] を** 選択してデバイスを再登録します。

このワークロードの移行フェーズ中に必要なアクション、または管理や使用状況への影響の詳細については [、Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)からの移行に関する Azure AD の追加情報の Azure Active Directory (Azure AD) に関する情報を確認してください。

## <a name="ios"></a>iOS

iOS デバイスでは、ユーザーはキャッシュされたアカウントを Microsoft Authenticator から手動で削除し、デバイスの登録を解除し、デバイス上のネイティブ アプリからサインアウトする必要があります。

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>手順 1: 存在する場合は、Microsoft Authenticator アプリからアカウントを削除する

1. Microsoft Authenticator アプリでアカウントをタップします。
2. 右上隅にある **[** 設定] アイコンをタップします。 [設定] アイコンが表示されない場合は、Microsoft Authenticator の最新バージョンを使用していない可能性があります。
3. [アカウントの **削除] ボタンをタップ** します。
4. この **デバイスのすべてのアプリをタップします**。
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>手順 2: Microsoft Authenticator アプリからデバイスの登録を解除する

1. 右上隅にあるメニュー アイコンをタップします。
2. [設定 **] をタップ** し、[デバイス **の登録] をタップします**。
4. アカウントが表示されている場合は、[デバイスの登録解除] **を** タップし、ダイアログ **で** [続行] をタップします。 その後、アカウントは表示されません。
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>手順 3: 必要に応じて個々のアプリからサインアウトする

ユーザーは、Outlook、Teams、OneDrive など、個々のアプリに移動し、それらのアプリからアカウントを削除できます。

## <a name="more-information"></a>詳細情報

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

移行を進む:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [追加の作業前作業](ms-cloud-germany-transition-add-pre-work.md)
- [Azure](ms-cloud-germany-transition-azure-ad.md)AD、[デバイス、エクスペリエンス](ms-cloud-germany-transition-add-devices.md)、[および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
