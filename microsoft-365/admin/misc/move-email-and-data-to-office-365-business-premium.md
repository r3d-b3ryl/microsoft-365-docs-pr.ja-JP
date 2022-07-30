---
title: メールとデータをMicrosoft 365 Business Standardに移動する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom:
- VSBFY23
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1062115d-e312-482a-bb5a-765235990f41
ROBOTS: NOINDEX
description: 新しいビジネス ID にデータを移動する方法について説明します。
ms.openlocfilehash: 59835134635c86a8970929fcb01f2d8de6320ca5
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085621"
---
# <a name="move-email-and-data-to-microsoft-365-business-standard"></a>メールとデータをMicrosoft 365 Business Standardに移動する

Microsoft 365 Business Standardにアップグレードすると、まったく新しい *ビジネス ID が提供されます*。 新しいメール アカウントと、ビジネス データ用に個別の OneDrive アカウントを利用できるようになります。 
  
個人データの一部を新しいビジネス ID に移動する場合は、次の手順に従います。
  
## <a name="onedrive"></a>[OneDrive](#tab/OneDrive)
  
 **OneDrive データをコピーする**
1. ハード ドライブに一時フォルダーを作成し、ビジネス向けに Microsoft 365 に移行するファイルを一時的に格納します。
    
2. Microsoft 365 Family サブスクリプションへの[https://onedrive.live.com/](https://onedrive.live.com/)アクセスに使用する Microsoft アカウントに移動してサインインします。 
    
3. Microsoft 365 for Business で使用するファイルを、手順 1. で作成したローカル フォルダーにコピーします。
    
 **ビジネス向け Microsoft 365 に OneDrive ファイルをインポートする**
1. [admin.microsoft.com](https://go.microsoft.com/fwlink/?LinkId=816877) に移動し、Microsoft 365 Apps for businessユーザー名とパスワードでサインインします。 
    
2. 左上の **アプリ起動ツール** アイコンを選択し、[ **OneDrive**] を選択します。
  
    > [!TIP]
    > OneDrive for Business を初めて開いたときに、OneDrive をセットアップする必要があります。 これが発生した場合は、[**OneDrive for Businessへようこそ**] ページで [**次へ**] を選択します。 OneDrive を設定したら、[ **OneDrive の準備完了**] を選択します。 
  
3. You'll be taken to an empty OneDrive folder. サブフォルダーを作成する場合は、[**新しい**\>フォルダー] を選択 **します**。

4. [ **アップロード]** を選択して、OneDrive ファイルをコピーしたハード ドライブからファイルをコピーします。 
  
    > [!NOTE]
    >  個々のファイルとファイルのグループ (特定のフォルダー内のすべてのファイルなど) を同時にアップロードできますが、OneDrive for Business にフォルダーをコピーすることはできません。代わりに、OneDrive for Business に必要なフォルダー構造を作成する必要があります。 >  手順 4 で作成したフォルダーにファイルをコピーする場合は、ファイルをアップロードする前に、そのフォルダーを開きます。そうしないと、ファイルはルート フォルダーにアップロードされます。ファイルのアップロード後、OneDrive for Business のフォルダー間でファイルを移動することもできます。 
  
## <a name="outlookemail"></a>[Outlook/メール](#tab/Outlook)
  
 **Outlook 2013 の情報を Outlook データ ファイルにエクスポートする**
1. Outlook データ ファイル (.pst) を作成する前に、Outlook の情報をエクスポートするアカウントが、デスクトップ バージョンの Outlook に既に追加されている必要があります。Outlook 2013 以上にアカウントを追加する方法については、「[Outlook 2010 または 2013 で Office 365 のメールを設定する](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b)」または「[Outlook for Mac 2011 で電子メールを設定する](https://support.microsoft.com/office/de372dc4-9648-4044-a76c-e8a60e178d54)」を参照してください。
    
2. 各ユーザーは、「[メール、連絡先、予定表を Outlook の .pst ファイルにエクスポートまたはバックアップする](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91)」の手順を実行する必要があります。
    
 **Outlook で新しいメール アカウントをセットアップする**
1. 各ユーザーは、ビジネス向け Microsoft 365 サブスクリプションに付属する新しいメール アカウントを設定する必要があります。 これを行うには、新しいメール アカウントのアドレスが必要です。 各ユーザーの電子メール アカウントは、ビジネス向け Microsoft 365 へのサインインに使用するユーザー名と同じです。 Sue@contoso.onmicrosoft.com や david@contoso.com のようなものになります。
    
2. 各ユーザーに、メール アカウントを Outlook に追加するように求めます。この方法については、「[Outlook 2010 または 2013 で Office 365 のメールを設定する](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b)」または「[Outlook for Mac 2011 で電子メールを設定する](https://support.microsoft.com/office/de372dc4-9648-4044-a76c-e8a60e178d54)」を参照してください。
    
 **Outlook データ ファイルから情報をインポートする**
1. これにより、PST ファイルに保存されている電子メール、予定表、タスク、連絡先が、ビジネス用の Microsoft 365 メール アカウントにマージされます。
    
2. PST ファイルに格納されている情報を Microsoft 365 for Business メール アカウントにインポートするには、各ユーザーに [Outlook .pst ファイルから電子メール、連絡先、予定表をインポートする手順を](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)完了させます。
    
---

