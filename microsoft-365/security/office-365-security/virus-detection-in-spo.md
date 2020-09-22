---
title: SharePoint Online のウイルス検出
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: ユーザーがアップロードするファイルで、SharePoint Online がウイルスを検出し、ユーザーがファイルをダウンロードまたは同期できないようにする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c65db566f165939d72429bcd61b7d0a880814e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196513"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive、Microsoft Teams でのウイルス検出

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft 365 は、ユーザーが SharePoint Online、OneDrive、Microsoft Teams にアップロードしたファイルのウイルスを検出することによって、マルウェアから環境を保護するのに役立ちます。 アップロードされたファイルはウイルススキャンされることがあります。 ファイルで感染が見つかると、プロパティが設定されて、そのファイルをダウンロードしたり、同期したりできなくなります。

> [!IMPORTANT]
> SharePoint Online のウイルス対策機能は、ウイルスを封じ込める 1 つの方法にすぎません。 これだけで、お客様の環境がマルウェアから保護されるわけではありません。 すべてのお客様が、マルウェア対策保護を評価してさまざまなレイヤーに実装し、ベスト プラクティスを適用してエンタープライズ インフラストラクチャを保護することをお勧めします。 戦略とベストプラクティスの詳細については、「 [セキュリティロードマップ](security-roadmap.md)」を参照してください。

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルが SharePoint Online にアップロードされたとき

Microsoft 365 では、一般的なウイルス検出エンジンを使用しています。 エンジンは SharePoint Online 内で非同期に実行され、アップロードされたファイルをスキャンします。 ヒューリスティックは、スキャンするファイルを決定するために使用されます。 ファイルでウイルスが見つかると、フラグが設定されて、そのファイルはダウンロードできなくなります。 2018年4月に、スキャンされたファイルの 25 MB の制限を削除しました。

動作は次のとおりです。

1. ユーザーがファイルを SharePoint Online にアップロードします。

2. SharePoint Online は、ファイルがスキャンの条件を満たしているかどうかを判断します。

3. ウイルス検出エンジンによってファイルがスキャンされます。

4. ウイルスが検出された場合、ウイルスエンジンはそのファイルが感染していることを示すプロパティを設定します。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>ブラウザーを使って感染したファイルをダウンロードしようとしても、

ファイルが感染している場合、ユーザーはブラウザーを使用して SharePoint Online からファイルをダウンロードすることはできません。

動作は次のとおりです。

1. Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、

2. ウイルスが検出されたという警告がユーザーに提示されます。 ユーザーには、ファイルをダウンロードして、独自のウイルス対策ソフトウェアを使用して駆除を試行するオプションが与えられます。

> [!NOTE]
>
> SharePoint Online PowerShell の[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットで*DisallowInfectedFileDownload*パラメーターを使用して、ウイルス対策の警告ウィンドウであっても、感染したファイルをユーザーがダウンロードできないようにすることができます。
>
> また、 *DisallowInfectedFileDownload* パラメーターを有効にすると、検出/ブロックされたファイルへのアクセスは、ユーザーと管理者に対して完全にブロックされることにも注意してください。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

ファイルの同期を 新しい OneDrive の同期クライアント (OneDrive.exe) と前の OneDrive for Business 同期クライアント (Groove.exe) のどちらを使用して行っても、そのファイルにウイルスが含まれている場合には同期クライアントでダウンロードができません。ファイルを同期できないという通知が同期クライアントに表示されます。

## <a name="extended-capabilities-with-office-365-atp"></a>Office 365 ATP の拡張機能

Sharepoint、OneDrive、Microsoft teams のために Office 365 ATP を有効にしたお客様は、SharePoint、onedrive、microsoft [teams 用の atp](turn-on-atp-for-spo-odb-and-teams.md) を有効にすることで、セキュリティ & コンプライアンスセンターを使用して、AV および ATP の検出用に検疫されたファイルを管理することができます。 [ATP のみ: セキュリティ & コンプライアンスセンターを使用して、検疫されたファイルを管理](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)します。

## <a name="more-information"></a>詳細情報

SharePoint Online のウイルス対策を構成する方法の詳細については、「 [脅威からの保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) 」および「 [sharepoint、OneDrive、Microsoft TEAMS 用の ATP を有効](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) にする」を参照してください。


