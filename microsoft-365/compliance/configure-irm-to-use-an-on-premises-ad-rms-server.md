---
title: オンプレミスの AD RMS サーバーを使用するように IRM を構成する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Active Directory Rights Management Service (EXCHANGE ONLINE RMS) サーバーを使用ADする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64d89d52b4e835c81ed1e2c8bbd54eaaae6f1823
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58572061"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>IRM を設定して、オンプレミスの AD RMS サーバーを使用する

Exchange Online の Information Rights Management (IRM) は、Exchange Online のオンプレミス展開で使用するために、Windows Server 2008 以降の情報保護テクノロジである Active Directory Rights Management サービス (AD RMS) を使用します。 IRM 保護を電子メールに適用するには、AD RMS 権利ポリシー テンプレートを電子メール メッセージに適用します。 権限はメッセージ自体に添付されているため、オンラインとオフラインの両方、および組織のファイアウォールの内外両方で保護が有効になります。

このトピックでは、AD RMS サーバーを使用するように IRM を構成する方法を示します。 Office 365 Message Encryption および Azure Rights Management の新機能の使用Office 365 Message Encryptionについては、「Azure Active Directory FAQ」[をOffice 365 Message Encryptionしてください](./ome-faq.yml)。

Exchange Online の IRM については、「[Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- このタスクの予想所要時間:30 分

- この手順を実行する際には、あらかじめアクセス許可が割り当てられている必要があります。 必要なアクセス許可を確認するには、「メッセージング ポリシーとコンプライアンスのアクセス許可」の「Information Rights Management」 [エントリを参照](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) してください。

- AD RMS サーバーは、Windows Server 2008 以降を実行している必要があります。 RMS を展開する方法の詳細についてはAD RMS クラスターの [インストールAD参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11))。

- Windows PowerShell のインストール方法と構成方法、およびサービスへの接続方法については、「[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- このトピックの手順に適用されるキーボード ショートカットの詳細については、「Exchange 管理センターのキーボード ショートカット」を[参照](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)Exchange Online。

> [!TIP]
> 問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。

## <a name="how-do-you-do-this"></a>実行方法
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>手順 1:AD RMS コンソールを使用して、AD RMS サーバーから信頼された発行ドメイン (TPD) をエクスポートします。

まず、信頼された発行ドメイン (TPD) を社内 AD RMS サーバーから XML ファイルにエクスポートします。TPD には RMS 機能を使用するために必要な以下の設定が含まれています。

- 証明書とライセンスの署名と暗号化に使用されるサーバー ライセンサー証明書 (SLC)

- ライセンスと発行に使用される URL

- TPD に固有の SLC を使用して作成された AD RMS 権利ポリシー テンプレート

TPD をインポートすると、その TPD はストレージに保存され、保護Exchange Online。

1. Active Directory Rights Management サービスのコンソールを開いて、AD RMS クラスターを展開します。

2. コンソール ツリーで、**[信頼ポリシー]** を展開してから、**[信頼された発行ドメイン]** をクリックします。

3. 結果ウィンドウで、エクスポートするドメインの証明書を選択します。

4. **[操作]** ウィンドウで、**[信頼された発行ドメインのエクスポート]** をクリックします。

5. **[発行ドメイン ファイル]** の **[名前を付けて保存]** をクリックして、ローカル コンピューター上の特定の場所にファイルを保存します。 ファイル名を入力し、ファイル名の拡張子を必ず指定し、[  `.xml` 保存] を **クリックします**。

6. **[パスワード]** ボックスと **[パスワードの確認入力]** ボックスに、信頼された発行ドメイン ファイルの暗号化に使用する強力なパスワードを入力します。このパスワードは、クラウドベースの電子メール組織に TPD をインポートするときに指定する必要があります。

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>手順 2: 管理シェルExchange使用して、TPD をインポートして管理Exchange Online

TPD を XML ファイルにエクスポートした後は、TPD を Exchange Online にインポートする必要があります。TPD をインポートすると、組織の AD RM テンプレートもインポートされます。最初の TPD をインポートすると、それがクラウドベース組織の既定の TPD になります。別の TPD をインポートする場合は、**Default** スイッチを使用してこの TPD を既定の TPD にし、ユーザーが使用できるようにすることができます。

TPD をインポートするには、Windows PowerShell で次のコマンドを実行します。

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

_ExtranetLicensingUrl_ パラメーターと _イントラネットLicensingUrl_ パラメーターの値は、コンソールActive Directory Rights Management サービスできます。 コンソール ツリーで AD RMS クラスターを選択します。 ライセンスの URL が結果ウィンドウに表示されます。 コンテンツを復号化する必要がある場合と使用する TPD を Exchange Online で決定する必要がある場合は、これらの URL が電子メール クライアントによって使用されます。

このコマンドを実行すると、パスワードの入力を求めるメッセージが表示されます。 TPD を AD RMS サーバーからエクスポートしたときに指定したパスワードを入力します。

たとえば、次のコマンドは、AD RMS サーバーからエクスポートして管理者アカウントのデスクトップに保存された XML ファイルを使用して、Exported TPD という名前の TPD をインポートします。Name パラメーターは TPD の名前を指定するために使用されます。

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

構文およびパラメーターの詳細については、「[Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain)」を参照してください。

#### <a name="how-do-you-know-this-step-worked"></a>このステップの検証方法

TPD が正常にインポートされたことを確認するには **、Get-RMSTrustedPublishingDomain** コマンドレットを実行して、組織の TPD をExchange Onlineします。 詳細については、「[Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain)」内の例を参照してください。

### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>手順 3: 管理シェルを使用Exchange RMS 権限ポリシー テンプレートAD配布する

TPD をインポートしたら、AD RMS 権利ポリシー テンプレートが配布されていることを確認する必要があります。 分散テンプレートは、Outlook on the web (以前は Outlook Web App) ユーザーに表示され、電子メール メッセージにテンプレートを適用できます。

既定の TPD に含まれているすべてのテンプレートの一覧を取得するには、次のコマンドを実行します。

```powershell
Get-RMSTemplate -Type All | fl
```

Type パラメーターの値  _が指定_ されている  `Archived` 場合、テンプレートはユーザーに表示されません。 既定の TPD 内の分散テンプレートだけが、既定の TPD でOutlook on the web。

テンプレートを配布するには、次のコマンドを実行します。

```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

たとえば、次のコマンドは、Company Confidential テンプレートをインポートします。

```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

構文とパラメーターの詳細については、「[Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate)」と「[Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate)」を参照してください。

**転送不可テンプレート**

既定の TPD を社内組織から Exchange Online にインポートすると、**Do Not Forward** という名前の AD RMS 権利ポリシー テンプレートが 1 つインポートされます。既定で、このテンプレートは、既定の TPD をインポートしたときに配布されます。**Set-RMSTemplate** コマンドレットを使用して **Do Not Forward** テンプレートを変更することはできません。

**Do Not Forward** テンプレートがメッセージに適用されている場合は、メッセージにアドレスが指定された受信者のみがメッセージを読むことができます。受信者が次の操作を行うことはできません。

- メッセージを別のユーザーに転送する。

- メッセージの内容をコピーする。

- メッセージを印刷する。

> [!IMPORTANT]
> **Do Not Forward** テンプレートは、サードパーティのスクリーン キャプチャ プログラムやカメラを使用してメッセージ内の情報がコピーされたり、ユーザーによって情報が書き写されるのを防げるわけではありません。

IRM 保護要件に合わせて、社内組織内の AD RMS サーバー上に追加の AD RMS 権利ポリシー テンプレートを作成できます。追加の AD RMS 権利ポリシー テンプレートを作成する場合は、TPD を社内 AD RMS サーバーから再びエクスポートして、クラウドベースの電子メール組織の TPD を更新する必要があります。

#### <a name="how-do-you-know-this-step-worked"></a>このステップの検証方法

RMS 権限ポリシー テンプレートが正常に配布AD確認するには **、Get-RMSTemplate** コマンドレットを実行してテンプレートのプロパティを確認します。 詳細については、「[Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate)」内の例を参照してください。

### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>手順 4: IRM を有効Exchange管理シェルを使用する

TPD をインポートして AD RMS 権利ポリシー テンプレートを配布したら、次のコマンドを実行して、クラウドベースの電子メール組織に対して IRM を有効にします。

```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

構文およびパラメーターの詳細については、「[Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)」を参照してください。

#### <a name="how-do-you-know-this-step-worked"></a>このステップの検証方法

IRM が正常に有効にされたことを確認するには[、Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration)コマンドレットを実行して、組織の IRM 構成Exchange Onlineします。

## <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法
<a name="sectionSection2"> </a>

TPD が正常にインポートされ、IRM が有効になったことを確認するには、次の手順を実行します。

- IRM の機能をテストするには、**Test-IRMConfiguration** コマンドレットを使用します。 詳細については [、「Test-IRMConfiguration」の「例 1」を参照してください](/powershell/module/exchange/test-irmconfiguration)。

- 新しいメッセージを Outlook on the webで作成し、拡張メニュー ([その他のオプション] アイコン) から [アクセス許可の設定] オプションを選択して IRM-protect ![ します ](../media/ITPro-EAC-MoreOptionsIcon.gif) 。
