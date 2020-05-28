---
title: メールとデータを Microsoft 365 Business Standard に移行する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1062115d-e312-482a-bb5a-765235990f41
ROBOTS: NOINDEX
description: 新しいビジネス id にデータを移動する方法について説明します。
ms.openlocfilehash: 03a8ff6b3cfab43d80401a10825a1c274e278ed9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399328"
---
# <a name="move-email-and-data-to-microsoft-365-business-standard"></a>メールとデータを Microsoft 365 Business Standard に移行する

Microsoft 365 Business Standard にアップグレードすると、新しい*ビジネス id*が提供されます。 新しいメール アカウントと、ビジネス データ用に個別の OneDrive アカウントを利用できるようになります。 
  
個人データの一部を新しいビジネス ID に移動する場合は、次の手順に従います。
  
## <a name="onedrive"></a>[OneDrive](#tab/OneDrive)
  
 **OneDrive データをコピーする**
1. Microsoft 365 for business に移行するファイルを一時的に保存するために、ハードドライブに一時フォルダーを作成します。
    
2. に移動 [https://onedrive.live.com/](https://onedrive.live.com/) し、microsoft 365 ファミリのサブスクリプションにアクセスするのに使用する microsoft アカウントを使用してサインインします。 
    
3. Microsoft 365 for business で使用するファイルを、手順1で作成したローカルフォルダーにコピーします。
    
 **一般法人向け Microsoft 365 に OneDrive ファイルをインポートする**
1. [Admin.microsoft.com](https://go.microsoft.com/fwlink/?LinkId=816877)にアクセスして、Microsoft 365 アプリのユーザー名とパスワードでサインインします。 
    
2. 左上の **アプリ起動ツール** アイコンを選択し、[ **OneDrive**] を選択します。
  
    > [!TIP]
    > OneDrive for Business を初めて開いたときに、OneDrive をセットアップする必要があります。 このような状況が発生した場合は、[ **OneDrive for business へようこそ**] ページで、[**次へ**] を選択します。 OneDrive をセットアップしたら、 **onedrive の準備ができ**ました。 
  
3. You'll be taken to an empty OneDrive folder. サブフォルダーを作成する場合は、[**新しい**フォルダー] を選択し \> **Folder**ます。

4. [**アップロード**] を選択して、OneDrive ファイルをコピーしたハードドライブからファイルをコピーします。 
  
    > [!NOTE]
    >  個々のファイルとファイルのグループ (特定のフォルダー内のすべてのファイルなど) を同時にアップロードできますが、OneDrive for Business にフォルダーをコピーすることはできません。代わりに、OneDrive for Business に必要なフォルダー構造を作成する必要があります。 >  手順 4 で作成したフォルダーにファイルをコピーする場合は、ファイルをアップロードする前に、そのフォルダーを開きます。そうしないと、ファイルはルート フォルダーにアップロードされます。ファイルのアップロード後、OneDrive for Business のフォルダー間でファイルを移動することもできます。 
  
## <a name="outlookemail"></a>[Outlook/メール](#tab/Outlook)
  
 **Outlook 2013 の情報を Outlook データ ファイルにエクスポートする**
1. Outlook データ ファイル (.pst) を作成する前に、Outlook の情報をエクスポートするアカウントが、デスクトップ バージョンの Outlook に既に追加されている必要があります。Outlook 2013 以上にアカウントを追加する方法については、「[Outlook 2010 または 2013 で Office 365 のメールを設定する](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)」または「[Outlook for Mac 2011 で電子メールを設定する](https://support.microsoft.com/en-us/office/set-up-email-in-mac-os-x-mail-de372dc4-9648-4044-a76c-e8a60e178d54)」を参照してください。
    
2. 各ユーザーは、「[メール、連絡先、予定表を Outlook の .pst ファイルにエクスポートまたはバックアップする](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)」の手順を実行する必要があります。
    
 **Outlook で新しいメール アカウントをセットアップする**
1. 各ユーザーは、Microsoft 365 for business サブスクリプションに付属していた新しいメールアカウントをセットアップする必要があります。 これを行うには、新しいメール アカウントのアドレスが必要です。 各ユーザーの電子メールアカウントは、Microsoft 365 for business にサインインするために使用するユーザー名と同じです。 Sue@contoso.onmicrosoft.com や david@contoso.com のようなものになります。
    
2. 各ユーザーに、メール アカウントを Outlook に追加するように求めます。この方法については、「[Outlook 2010 または 2013 で Office 365 のメールを設定する](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)」または「[Outlook for Mac 2011 で電子メールを設定する](https://support.microsoft.com/en-us/office/set-up-email-in-mac-os-x-mail-de372dc4-9648-4044-a76c-e8a60e178d54)」を参照してください。
    
 **Outlook データ ファイルから情報をインポートする**
1. これにより、PST ファイルに格納されている電子メール、予定表、タスク、連絡先が Microsoft 365 for business の電子メールアカウントに結合されます。
    
2. PST ファイルに格納されている情報を Microsoft 365 for business の電子メールアカウントにインポートするには、各ユーザーが「 [Outlook .pst ファイルからメール、連絡先、予定表をインポート](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac.aspx)する」の手順を完了している必要があります。
    
---

