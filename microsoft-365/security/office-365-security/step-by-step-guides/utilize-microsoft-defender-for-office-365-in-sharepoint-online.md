---
title: SharePoint Online でMicrosoft Defender for Office 365を使用する
description: SharePoint Online と OneDrive for BusinessでMicrosoft Defender for Office 365を使用して値を取得できるようにする手順
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTBen
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 63b9a7b4b3e61f6c0bf8e6ce0d5c1f9bc490bbbc
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67277276"
---
# <a name="use-microsoft-defender-for-office-365-with-sharepoint-online"></a>SharePoint Online でMicrosoft Defender for Office 365を使用する

Microsoft Office SharePoint Onlineは、広く使用されているユーザー コラボレーションとファイル ストレージ ツールです。 次の手順は、SharePoint Online の攻撃領域を減らすのに役立ち、このコラボレーション ツールを組織内でセキュリティで保護するのに役立ちます。 ただし、セキュリティと生産性のバランスがあり、これらの手順のすべてが組織のリスク プロファイルに関連するわけではないことに注意してください。 そのバランスを見て、テストし、維持します。

## <a name="what-youll-need"></a>必要なもの

- Microsoft Defender for Office 365 プラン 1
- 十分なアクセス許可 (SharePoint 管理者/セキュリティ管理者)。
- Microsoft Office SharePoint Online (Microsoft 365 の一部)。
- これらの手順を実行するには、5 分から 10 分です。

## <a name="turn-on-microsoft-defender-for-office-365-in-sharepoint-online"></a>SharePoint Online でMicrosoft Defender for Office 365を有効にする
Microsoft Defender for Office 365 **(aka.ms/trymdo で利用可能な無料の 90 日間の評価)** のライセンスを取得している場合は、Microsoft Teams 内のゼロデイ マルウェアとクリック保護の時間からのシームレスな保護を確保できます。

詳細については、「[手順 1: Microsoft 365 Defender ポータルを使用して、SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にする](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams#step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams)」を参照してください。

1.  [セキュリティ センターの安全な添付ファイル構成ページ](https://security.microsoft.com/safeattachmentv2)にサインインします。
1.  **[グローバル設定]** を選択します。
1.  **SharePoint、OneDrive、および Microsoft Teams のDefender for Office 365をオンに** 設定していることを確認 **します。**
1.  [セキュリティ センターの [安全なリンク] 構成ページ](https://security.microsoft.com/safelinksv2)に移動します。
1.  **[保存]** を選択します。

## <a name="stop-infected-file-downloads-from-sharepoint-online"></a>SharePoint Online から感染したファイルのダウンロードを停止する

既定では、SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルによって検出された悪意のあるファイルを開いたり、移動したり、コピーしたり、共有したりすることはできません。 ただし、[ *ダウンロード* ] オプションは引き続き使用でき、 *無効にする* 必要があります。 

詳細については、「 [手順 2: (*推奨*) SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードできないようにする](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)」を参照してください。

1.  [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) を開いて接続します。
1.  **Set-SPOTenant -DisallowInfectedFileDownload $true** コマンドを実行します。

### <a name="further-reading"></a>その他の読み取り
[SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項](/microsoft-365/security/office-365-security/sharepoint-file-access-policies)
