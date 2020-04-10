---
title: Office 365 Business Premium にメールとデータを移動する
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1062115d-e312-482a-bb5a-765235990f41
ROBOTS: NOINDEX
description: 新しいビジネス id にデータを移動する方法について説明します。
ms.openlocfilehash: fc0df5e919370395480cdafbaaee10b0d844f088
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209678"
---
# <a name="move-email-and-data-to-office-365-business-premium"></a>Office 365 Business Premium にメールとデータを移動する

Office 365 Business Premium にアップグレードすると、新しい*ビジネス id*が提供されます。 新しいメール アカウントと、ビジネス データ用に個別の OneDrive アカウントを利用できるようになります。 
  
個人データの一部を新しいビジネス ID に移動する場合は、次の手順に従います。
  
## <a name="onedrive"></a>[OneDrive](#tab/OneDrive)
  
 **OneDrive データをコピーする**
1. 一般法人向け Office 365 に移行するファイルを一時的に保存するために、ハード ドライブに一時的なフォルダーを作成します。
    
2. [https://onedrive.live.com/](https://onedrive.live.com/) にアクセスし、家庭向け Office 365 サブスクリプションへのアクセスに使用している Microsoft アカウントを使ってサインインします。 
    
3. 一般法人向け Office 365 で使用するファイルを手順 1 で作成したローカル フォルダーにコピーします。
    
 **一般法人向け Office 365 に OneDrive ファイルをインポートする**
1. [Admin.microsoft.com](https://go.microsoft.com/fwlink/?LinkId=816877)に移動し、Office 365 Business ユーザー名とパスワードでサインインします。 
    
2. 左上の **アプリ起動ツール** アイコンを選択し、[ **OneDrive**] を選択します。
  
    > [!TIP]
    > OneDrive for Business を初めて開いたときに、OneDrive をセットアップする必要があります。 このような状況が発生した場合は、[ **OneDrive for business へようこそ**] ページで、[**次へ**] を選択します。 OneDrive をセットアップしたら、 **onedrive の準備ができ**ました。 
  
3. You'll be taken to an empty OneDrive folder. サブフォルダーを作成する場合は、[**新しい** \> **フォルダー**] を選択します。

4. [**アップロード**] を選択して、OneDrive ファイルをコピーしたハードドライブからファイルをコピーします。 
  
    > [!NOTE]
    >  個々のファイルとファイルのグループ (特定のフォルダー内のすべてのファイルなど) を同時にアップロードできますが、OneDrive for Business にフォルダーをコピーすることはできません。代わりに、OneDrive for Business に必要なフォルダー構造を作成する必要があります。 >  手順 4 で作成したフォルダーにファイルをコピーする場合は、ファイルをアップロードする前に、そのフォルダーを開きます。そうしないと、ファイルはルート フォルダーにアップロードされます。ファイルのアップロード後、OneDrive for Business のフォルダー間でファイルを移動することもできます。 
  
## <a name="outlookemail"></a>[Outlook/メール](#tab/Outlook)
  
 **Outlook 2013 の情報を Outlook データ ファイルにエクスポートする**
1. Outlook データ ファイル (.pst) を作成する前に、Outlook の情報をエクスポートするアカウントが、デスクトップ バージョンの Outlook に既に追加されている必要があります。Outlook 2013 以上にアカウントを追加する方法については、「[Outlook 2010 または 2013 で Office 365 のメールを設定する](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)」または「[Outlook for Mac 2011 で電子メールを設定する](https://support.office.com/article/d7b404a0-6e18-4d95-bed8-2de7661563ca.aspx)」を参照してください。
    
2. 各ユーザーは、「[メール、連絡先、予定表を Outlook の .pst ファイルにエクスポートまたはバックアップする](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)」の手順を実行する必要があります。
    
 **Outlook で新しいメール アカウントをセットアップする**
1. 各ユーザーは、一般法人向け Office 365 サブスクリプションに付属している新しいメール アカウントをセットアップする必要があります。これを行うには、新しいメール アカウントのアドレスが必要です。各ユーザーのメール アカウントは一般法人向け Office 365 にサインインするために使用するユーザー名と同じです。Sue@contoso.onmicrosoft.com や david@contoso.com のようなものになります。
    
2. 各ユーザーに、メール アカウントを Outlook に追加するように求めます。この方法については、「[Outlook 2010 または 2013 で Office 365 のメールを設定する](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)」または「[Outlook for Mac 2011 で電子メールを設定する](https://support.office.com/article/d7b404a0-6e18-4d95-bed8-2de7661563ca.aspx)」を参照してください。
    
 **Outlook データ ファイルから情報をインポートする**
1. この操作を行うと、PST ファイルに保存されているメール、予定表、タスク、連絡先が一般法人向け Office 365 のメール アカウントに結合されます。
    
2. PST ファイルに保存されている情報を一般法人向け Office 365 メール アカウントにインポートするには、各ユーザーに「[Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac.aspx)」の手順を実行してもらいます。
    
---

