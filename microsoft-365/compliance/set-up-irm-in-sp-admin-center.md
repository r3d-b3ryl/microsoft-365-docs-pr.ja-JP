---
title: SharePoint 管理センターで Information Rights Management (IRM) を設定する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Microsoft Azure Active Directory Rights Management Services (RMS) を使用して SharePoint Online IRM を使用して SharePoint リストとドキュメントライブラリを保護する方法について説明します。
ms.openlocfilehash: ab045c2319897a98bffd14f898dd254b06890bee
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222374"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>SharePoint 管理センターで Information Rights Management (IRM) を設定する

## <a name="introduction"></a>概要

SharePoint Online では、リストおよびライブラリのレベルでファイルに IRM 保護が適用されます。 組織で IRM 保護を使用するには、まず、Rights Management をセットアップしておく必要があります。 IRM は Azure Information Protection の Azure Rights Management サービスを利用して、暗号化と使用制限の割り当てを実施します。 一部の Microsoft 365 プランには、Azure Rights Management は含まれていますが、すべてではありません。 詳細については、「 [Office アプリケーションとサービスが Azure Rights Management をサポートする方法](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)」を参照してください。
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>SharePoint 管理センターを使用して IRM サービスを有効にする

組織で SharePoint リストとライブラリを IRM で保護するには、まず、組織の Rights Management サービスをアクティブ化する必要があります。 [Azure Rights Management をアクティブ化](https://docs.microsoft.com/information-protection/deploy-use/activate-service)する方法については、「」を参照してください。 Rights Management サービスを有効にするには、グローバル管理者特権を持つ職場または学校のアカウントを使用する必要があります。 そうしないと、SharePoint Online で IRM 機能を使用できなくなります。
  
Rights Management サービスをアクティブ化した後、SharePoint 管理センターにサインインして IRM を有効にします。
  
1. グローバル管理者または SharePoint 管理者としてサインインします。
    
2. 左上のアプリ起動ツールのアイコン ![Office 365 のアプリ起動ツールのアイコン](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) を選択し、**[管理者]** を選択して Microsoft 365 管理センターを開きます (管理者のタイルが表示されていない場合は、組織の管理者権限がありません。) 
    
3. 左側のウィンドウで、**[管理センター]** \> **[SharePoint]** の順に選択します。
    
4. 左側のウィンドウで、[**設定**] を選択し、[**クラシック設定] ページ**を選択します。
    
5. [ **Information Rights Management (irm)** ] セクションで、[**構成で指定された Irm サービスを使用する**] を選択し、[ **irm 設定の更新**] を選択します。 IRM 設定を更新した後、組織内のユーザーは、SharePoint リストとドキュメントライブラリで IRM を使用することができます。 ただし、[ライブラリの設定] および [リストの設定] に表示されるまでに最大1時間かかる場合があります。
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM-SharePoint ドキュメントライブラリとリストを有効にする
<a name="__toc220831191"> </a>

IRM 設定を更新すると、サイト所有者は SharePoint リストとドキュメントライブラリを IRM で保護できます。 詳細については、「[リストまたはライブラリに Information Rights Management を適用する](apply-irm-to-a-list-or-library.md)」を参照してください。
  
サイト所有者は、リストまたはライブラリで IRM を有効にすると、そのリストまたはライブラリでサポートされているファイルの種類を保護できます。 ライブラリで IRM が有効になっている場合、rights management はそのライブラリ内のすべてのファイルに適用されます。 リストに対して IRM を有効にする場合、rights management は、実際のリストアイテムではなく、リストアイテムに添付されているファイルにのみ適用されます。
  
ユーザーが IRM 対応リストまたはライブラリにファイルをダウンロードすると、承認されたユーザーのみがファイルを表示できるように、ファイルが暗号化されます。 また、各権限管理ファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスが含まれています。 一般的な制限としては、ファイルを読み取り専用にし、テキストのコピーを無効にして、ユーザーがローカルコピーを保存しないようにしたり、ファイルを印刷できないようにしたりすることがあります。 IRM がサポートするファイルの種類を読み取ることができるクライアントプログラムは、権限が管理されたファイル内の発行ライセンスを使用して、これらの制限を適用します。 これは、権限が管理されたファイルがダウンロードされた後も保護を保持する方法です。 リストまたはライブラリで IRM を有効にするには、「[リストまたはライブラリへの Information Rights Management の適用](apply-irm-to-a-list-or-library.md)」を参照してください。
  
ブラウザーで Office を使用して、IRM が有効なライブラリ内のドキュメントを作成または編集することはできません。 代わりに、一度に1人のユーザーが IRM で暗号化されたファイルをダウンロードして編集することができます。 チェックインとチェックアウトを使用して、複数のユーザーにまたがる*共同編集*または作成を管理します。 
  
IRM で保護されたライブラリから PDF ファイルをダウンロードすると、Microsoft 365 は保護された PDF ファイルを作成します。 ファイルの拡張子は変わりませんが、ファイルは保護されます。 このファイルを表示するには、Azure Information Protection viewer、完全な Azure Information Protection クライアント、または保護された PDF ファイルの表示をサポートする別のアプリケーションが必要です。 
  
SharePoint Online では、次の種類のファイルの暗号化がサポートされています。
  
- PDF
    
- 次の Microsoft Office プログラムの97-2003 ファイル形式: Word、Excel、および PowerPoint
    
- Office Open XML 形式の次の Microsoft Office プログラム: Word、Excel、および PowerPoint
    
- XML Paper Specification (XPS) 形式
 
> [!NOTE]
> SharePoint はアップロード時にドキュメントを開く必要があるため、IRM 保護を保護されたドキュメント (デジタル署名された PDF ファイルなど) に適用することはできません。 

## <a name="next-steps"></a>次の手順
<a name="__toc220831191"> </a>

SharePoint Online の IRM を有効にしたら、[リストとライブラリへの rights management の適用] を開始できます。 詳細については、「[リストまたはライブラリに Information Rights Management を適用する](apply-irm-to-a-list-or-library.md)」を参照してください。
  
SharePoint 用の新しい OneDrive 同期クライアントでは、IRM で保護された SharePoint ドキュメントライブラリと OneDrive の場所の同期がサポートされるようになりました (ライブラリの IRM 設定でドキュメントアクセス権の有効期限が設定されていない場合)。 詳細については、または新しい同期クライアントの展開を開始するには、「 [Windows 用の新しい OneDrive 同期クライアントを展開](https://docs.microsoft.com/onedrive/deploy-on-windows)する」を参照してください。
  
[ページのトップへ](#introduction)  
