---
title: Microsoft クラウドの移行に関するその他のデバイス情報
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
description: '概要: 新しいドイツデータセンターリージョンの Microsoft Cloud ドイツ (Microsoft Cloud Deut上陸ランド) から Office 365 services に移行する場合の、サービスに関する追加のデバイス情報。'
ms.openlocfilehash: da05a3c2eb6a8d579c53d403a1ef575c389eda12
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551955"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft クラウドの移行に関するその他のデバイス情報

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**組織に影響があるかどうかを確認するには、どうすればよいですか?**

管理者は、 `https://portal.microsoftazure.de` 登録済みデバイスがあるかどうかを確認する必要があります。 組織にデバイスが登録されている場合は、影響を受けます。

**ユーザーにどのような影響があるか。**

登録済みデバイスのユーザーは、移行後に [AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 移行フェーズを終了した後、サインインできなくなります。  

組織が Microsoft Cloud Deut上陸陸から切断される前に、すべてのデバイスがワールドワイドエンドポイントに登録されていることを確認してください。
  
**ユーザーが自分のデバイスを再登録するのはいつですか。**

[Microsoft Cloud Deut/陸](ms-cloud-germany-transition.md#how-is-the-migration-organized)の移行フェーズとは別に、デバイスの登録を解除して再登録することは、成功にとって不可欠です。

**移行後にデバイスの状態を復元するにはどうすればよいですか?**

Azure AD に登録されているハイブリッド Azure AD –参加済みおよび会社所有の Windows デバイスでは、管理者は、古いデバイス状態の登録を解除するリモートでトリガーされたワークフローを使用してこれらのデバイスの移行を管理できます。
  
他のすべてのデバイス (Azure AD に登録されている個人の Windows デバイスを含む) については、エンドユーザーはこれらの手順を手動で実行する必要があります。 Azure AD と参加しているデバイスの場合、ユーザーはローカル管理者アカウントを持っている必要があります。デバイスの登録を解除してから登録し直す必要があります。

Microsoft は、デバイス状態を正常に復元する方法についての指示を公開します。 
 
**パブリッククラウドにすべてのデバイスが登録されていることを確認するには、どうすればよいですか?**

デバイスがパブリッククラウドに登録されているかどうかを確認するには、Azure AD ポータルから Excel スプレッドシートにデバイスの一覧をエクスポートしてダウンロードする必要があります。 その後、 [Microsoft Cloud Deut上陸土地](ms-cloud-germany-transition.md#how-is-the-migration-organized)移行フェーズとは別に、登録されているデバイス ( _registeredtime_ 列を使用) にフィルターを適用します。

テナントの移行後はデバイスの登録が非アクティブになり、有効または無効にすることはできません。 Intune を使用しない場合は、サブスクリプションにサインインして、次のコマンドを実行してオプションを再度アクティブ化します。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Windows ハイブリッド Azure AD join

### <a name="windows-down-level"></a>Windows ダウンレベル

_Windows ダウンレベルデバイス_ は、以前のバージョンの Windows (windows 8.1 や windows 7 など) を現在実行している windows デバイス、または2019および2016より前のバージョンの windows Server を実行している windows デバイスです。 そのようなデバイスが以前に登録されていた場合は、それらのデバイスの登録を解除してから登録し直す必要があります。 

Windows のダウンレベルデバイスが以前 Azure AD に参加していたかどうかを確認するには、デバイス上で次のコマンドを使用します。

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

デバイスが以前 Azure AD に参加していて、デバイスがグローバルな Azure AD エンドポイントにネットワーク接続されている場合は、次の出力が表示されます。

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

影響を受けるデバイスの "デバイス状態" に "Unknown" という値が設定されます。 出力が "デバイスが参加していません" または "Device state" の値が "Ok" の場合は、次のガイダンスは無視してください。

デバイスが (deviceId、拇印などを使用して) 結合されていて、"Device state" 値が "Unknown" であることを示すデバイスに対してのみ、次のコマンドを実行する必要があります。このようなダウンレベルデバイスでは、ドメインユーザーがサインインしています。

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

上記のコマンドは、Windows ダウンレベルデバイスでサインインしたドメインユーザーごとに1回だけ実行する必要があります。 このコマンドは、サインインしているドメインユーザーのコンテキストで実行する必要があります。 

ユーザーが後でサインインしたときに、このコマンドを実行しないように十分な注意を払う必要があります。 上記のコマンドを実行すると、サインインしたユーザーについて、ローカルハイブリッド Azure AD に参加しているコンピューターの参加状態がクリアされます。 また、コンピューターが依然としてハイブリッド Azure AD として構成されている場合は、テナントに参加すると、ユーザーが再度サインインするときに参加が試みられます。

### <a name="windows-current"></a>現在の Windows

#### <a name="unjoin"></a>切断

以前に Windows 10 デバイスが Azure AD に参加していたかどうかを確認するには、デバイス上で次のコマンドを実行します。

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

デバイスがハイブリッド Azure AD に参加している場合は、管理者に次の出力が表示されます。

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

出力が "AzureAdJoined: No" の場合は、次のガイダンスは無視してください。

デバイスが Azure AD に参加していることを示すデバイスに対してのみ、次のコマンドを管理者として実行して、デバイスの結合状態を削除します。

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

上記のコマンドは、Windows デバイスの管理コンテキストで1回だけ実行する必要があります。

#### <a name="hybrid-ad-joinre-registration"></a>ハイブリッド AD Join\ 再登録

デバイスがグローバルな Azure AD エンドポイントにネットワーク接続されている限り、ユーザーまたは管理者の介入なしに、デバイスは自動的に Azure AD に参加します。 


## <a name="windows-azure-ad-join"></a>Windows Azure AD Join

### <a name="unjoin"></a>切断

Windows 10 デバイスが以前 Azure AD に参加していたかどうかを確認するには、ユーザーまたは管理者がデバイス上で次のコマンドを実行します。

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

出力が "AzureAdJoined: NO" の場合は、次のガイダンスは無視してください。

ユーザー: デバイスが Azure AD に参加している場合、ユーザーはそのデバイスを設定から離すことができます。 Azure AD からデバイスを unjoining する前に、デバイスのローカル管理者アカウントが存在することを確認します。 ローカル管理者アカウントは、デバイスにサインインし直す必要があります。

管理者: 組織の管理者が Azure AD に参加しているユーザーのデバイスを離れる場合は、グループポリシーなどのメカニズムを使用して、各デバイスで次のコマンドを実行します。 管理者は、Azure AD からデバイスを unjoining する前に、デバイスにローカル管理者アカウントがあることを確認する必要があります。 ローカル管理者アカウントは、デバイスにサインインし直すために必要です。

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

上記のコマンドは、Windows デバイスの管理コンテキストで1回だけ実行する必要があります。 

### <a name="azure-ad-joinre-registration"></a>Azure AD 参加/再登録

ユーザーは、Windows の設定から Azure AD にデバイスを参加させることができます。 **設定 > アカウント > Access の職場または学校 > Connect**。
 

## <a name="windows-azure-ad-registered-company-owned"></a>登録されている Windows Azure AD (会社の所有)

Windows 10 デバイスが Azure AD に登録されているかどうかを確認するには、デバイスで次のコマンドを実行します。

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

デバイスが Azure AD に登録されている場合は、次の出力が表示されます。

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

デバイス上の既存の Azure AD 登録アカウントを削除するには、次のようにします。

- デバイス上の Azure AD に登録されているアカウントを削除するには、次の場所からダウンロードできる CleanupWPJ を使用します。 [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)。

- ZIP ファイルを展開して、 **Wpjcleanup コマンド** を実行します。 このツールは、デバイス上の Windows のバージョンに基づいて、適切な実行可能ファイルを起動します。

- グループポリシーなどのメカニズムを使用すると、管理者はデバイス上でサインインしているユーザーのコンテキストで、デバイス上でコマンドを実行できます。

Azure AD にデバイスを登録するために Web アカウントマネージャーの音声ガイダンスを無効にするには、次のレジストリ値を追加します。 

- 場所: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- 型: DWORD (32 ビット)
- 名前: BlockAADWorkplaceJoin
- 値のデータ: 1

このレジストリ値が存在すると、workplace join がブロックされ、ユーザーがデバイスに参加するように求めるメッセージを表示できなくなります。

## <a name="android"></a>Android

Android の場合、ユーザーはデバイスの登録を解除して、再登録する必要があります。 これは、Microsoft Authenticator アプリまたはポータルサイトアプリを使用して行うことができます。 

- Microsoft Authenticator アプリから、ユーザーは [ **設定 > デバイス登録**] に移動できます。 この場合、ユーザーは自分のデバイスの登録を解除して再登録することができます。
 
- ポータルサイトから、ユーザーは [ **デバイス** ] タブに移動してデバイスを削除できます。 その後、会社のポータルを使用してデバイスを再登録します。
 
- ユーザーは、[アカウント設定] ページからアカウントを削除してから、もう一度作業アカウントを追加することによって、登録を解除して再登録することもできます。

Microsoft Authenticator アプリを使用して Android でデバイスの登録を解除して再登録するには、次のようにします。

1.  Microsoft Authenticator アプリを開いて [ **設定**] に移動します。
2.  [ **デバイス登録**] を選択します。
3.  [ **登録解除**] を選択してデバイスの登録を解除します。
4.  [ **デバイスの登録**] で、電子メールアドレスを入力してデバイスを再登録し、[ **登録**] を選択します。

Android の設定ページを使用して Android デバイスの登録を解除して再登録するには、次のようにします。

1.  [ **デバイスの設定** ] を開いて、[ **アカウント**] に移動します。
2.  再登録するワークアカウントを選択し、[ **アカウントの削除**] を選択します。
3.  アカウントが削除されたら、[ **アカウント** ] ページで、[ **アカウントの追加 > 作業アカウント**] を選択します。
4.  **Workplace Join** の場合は、電子メールアドレスを入力し、[**参加**] を選択してデバイスの登録を完了します。

ポータルサイトから Android でデバイスの登録を解除して再登録するには、次のようにします。

1.  ポータルサイトを起動して、[ **デバイス** ] タブに移動します。
2.  デバイスを選択して、デバイスの詳細を表示します。
3.  省略記号 (3 つのドット) メニューから、[ **デバイスの削除**] を選択し、ダイアログで確認して削除を完了します。
4.  これで、ポータルサイトアプリからログアウトできるようになります。 [ **サインイン** ] を選択して、デバイスを再登録します。

このワークロードの移行フェーズ中に必要なすべての操作、または管理または使用に対する影響の詳細については、 [Microsoft Cloud Deut上陸陸からの移行に関するその他の一般的な情報](ms-cloud-germany-transition-add-general.md#azure-active-directory)について、Azure Active Directory に関する情報を参照してください。

## <a name="ios"></a>iOS

IOS デバイスでは、ユーザーはキャッシュされたアカウントを Microsoft Authenticator から手動で削除し、デバイスの登録を解除して、デバイス上の任意のネイティブアプリからサインアウトする必要があります。

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>手順 1: 存在する場合は、Microsoft Authenticator アプリからアカウントを削除します。

1. Microsoft Authenticator アプリでアカウントをタップします。
2. 右上隅の [ **設定** ] アイコンをタップします。 [ **設定** ] アイコンが表示されない場合は、最新バージョンの Microsoft Authenticator を使用していない可能性があります。
3. [ **アカウントの削除** ] ボタンをタップします。
4. **このデバイス上のすべてのアプリを** タップします。
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>手順 2: Microsoft Authenticator アプリからデバイスの登録を解除する

1. 右上隅にあるメニューアイコンをタップします。
2. [ **設定** ]、[ **デバイス登録**] の順にタップします。
4. アカウントが表示されている場合は、[ **デバイスの登録を解除** して **続行** する] をタップします。 その後、アカウントは何も表示されません。
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>手順 3: 必要に応じて個々のアプリからサインアウトする

ユーザーは、Outlook、Teams、OneDrive などの個別のアプリに移動したり、それらのアプリからアカウントを削除したりできます。

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
