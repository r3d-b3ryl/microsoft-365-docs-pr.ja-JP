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
description: SharePoint リストとドキュメント ライブラリを保護するために、Microsoft Azure Active Directory Rights Management サービス (RMS) を介して SharePoint Online IRM を使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919403"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>SharePoint 管理センターで Information Rights Management (IRM) を設定する

SharePoint Online では、リストおよびライブラリのレベルでファイルに IRM 保護が適用されます。 組織で IRM 保護を使用するには、まず、Rights Management をセットアップしておく必要があります。 IRM は Azure Information Protection の Azure Rights Management サービスを利用して、暗号化と使用制限の割り当てを実施します。 一部の Microsoft 365 プランには Azure Rights Management が含まれますが、すべてではありません。 詳細については、「アプリケーションとサービス [が Azure Rights Management をOfficeする方法」を参照してください](/azure/information-protection/understand-explore/office-apps-services-support)。
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>SharePoint 管理センターを使用して IRM サービスを有効にする

組織が SharePoint リストとライブラリを IRM で保護するには、まず組織の Rights Management サービスをアクティブ化する必要があります。 詳細については [、「Azure Rights Management のアクティブ化」を参照してください](/information-protection/deploy-use/activate-service)。 Rights Management サービスを有効にするには、グローバル管理者特権を持つ仕事または学校のアカウントを使用する必要があります。 それ以外の場合は、SharePoint Online で IRM 機能を使用することはできません。
  
Rights Management サービスをアクティブ化した後、SharePoint 管理センターにサインインして IRM を有効にしてください。
  
1. グローバル管理者または SharePoint 管理者としてサインインします。
    
2. 左上のアプリ起動ツールのアイコン ![Office 365 のアプリ起動ツールのアイコン](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) を選択し、**[管理者]** を選択して Microsoft 365 管理センターを開きます ([管理者] タイルが表示されていない場合は、組織内に管理者のアクセス許可を持つ必要があります)。 
    
3. 左側のウィンドウで、**[管理センター]** \> **[SharePoint]** の順に選択します。
    
4. 左側のウィンドウで、[設定] を **選択し**、[クラシック設定] **ページを選択します**。
    
5. [Information **Rights Management (IRM) セクションで** 、[構成で指定された IRM サービスを使用する] を選択し **、[IRM** 設定の更新] **を選択します**。 IRM 設定を更新すると、組織内のユーザーは SharePoint リストとドキュメント ライブラリで IRM の使用を開始できます。 ただし、これを行うオプションは、[ライブラリの設定] と [リストの設定] に表示されるのに最大で 1 時間かかる場合があります。
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM-enable SharePoint ドキュメント ライブラリとリスト
<a name="__toc220831191"> </a>

IRM 設定を更新すると、サイト所有者は自分の SharePoint リストとドキュメント ライブラリを IRM で保護できます。 詳細については、「Apply [Information Rights Management to a list or library」を参照してください](apply-irm-to-a-list-or-library.md)。
  
サイト所有者がリストまたはライブラリの IRM を有効にした場合、そのリストまたはライブラリでサポートされているファイルの種類を保護できます。 IRM がライブラリに対して有効になっている場合、権限管理はそのライブラリ内のすべてのファイルに適用されます。 リストの IRM を有効にした場合、権限管理は、実際のリスト アイテムではなく、リスト アイテムに添付されているファイルにのみ適用されます。
  
ユーザーが IRM が有効なリストまたはライブラリ内のファイルをダウンロードすると、ファイルは暗号化され、承認されたユーザーのみがファイルを表示できます。 各権限管理ファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスも含まれている。 一般的な制限としては、ファイルの読み取り専用化、テキストのコピーの無効化、ユーザーによるローカル コピーの保存の防止、ファイルの印刷の防止が含まれます。 IRM でサポートされているファイルの種類を読み取るクライアント プログラムは、権限管理ファイル内の発行ライセンスを使用して、これらの制限を適用します。 これは、権限で管理されたファイルがダウンロードされた後でも保護を保持する方法です。 リストまたはライブラリで IRM を有効にするには、「情報権限管理をリストまたはライブラリに適用 [する」を参照してください](apply-irm-to-a-list-or-library.md)。
  
IRM が有効なライブラリ内のドキュメントを作成または編集するには、ブラウザー Officeを使用します。 代わりに、一度に 1 人のユーザーが IRM で暗号化されたファイルをダウンロードして編集できます。 チェックインとチェックアウトを使用して、複数のユーザー間で共同  *編集、または*  オーサリングを管理します。 
  
IRM で保護されたライブラリから PDF ファイルをダウンロードすると、Microsoft 365 は保護された PDF ファイルを作成します。 ファイルの拡張子は変更されませんが、ファイルは保護されています。 このファイルを表示するには、Azure Information Protection ビューアー、Azure Information Protection クライアント全体、または保護された PDF ファイルの表示をサポートする別のアプリケーションが必要です。 
  
SharePoint Online では、次の種類のファイルの暗号化がサポートされています。
  
- PDF
    
- Word、Excel、PowerPoint の 97-2003 ファイル形式は、次Microsoft Officeプログラムの形式です。
    
- 次Officeプログラムの Open XML Microsoft Office形式: Word、Excel、および PowerPoint
    
- XML 用紙仕様 (XPS) 形式
 
> [!NOTE]
> SharePoint はアップロード時にドキュメントを開く必要があるので、保護されたドキュメント (デジタル署名された PDF ファイルなど) には IRM 保護を適用できません。 

## <a name="next-steps"></a>次の手順
<a name="__toc220831191"> </a>

SharePoint Online の IRM を有効にしたら、リストとライブラリへの権限管理の適用を開始できます。 詳細については、「 [情報権限管理をリストまたはライブラリに適用する」を参照してください](apply-irm-to-a-list-or-library.md)。
  
Windows 用の新しい OneDrive 同期クライアントは、IRM で保護された SharePoint ドキュメント ライブラリと OneDrive の場所の同期をサポートしています (ライブラリの IRM 設定がドキュメント アクセス権を期限切れに設定されていない限り)。 詳細については、または新しい同期クライアントの展開を開始するには、「新しい OneDrive 同期クライアントを Windows 用に展開する」を [参照してください](/onedrive/deploy-on-windows)。
  
[ページのトップへ](set-up-irm-in-sp-admin-center.md)