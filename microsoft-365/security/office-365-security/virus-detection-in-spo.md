---
title: SharePoint Online、OneDrive、Microsoft Teams の組み込みウイルス対策
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: SharePoint Online が、ユーザーがアップロードするファイル内のウイルスを検出し、ユーザーがファイルをダウンロードまたは同期するのを防ぐ方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286503"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive、Microsoft Teams の組み込みウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)

Microsoft 365 は、ユーザーが SharePoint Online、OneDrive、および Microsoft Teams にアップロードするファイルをスキャンするために一般的なウイルス検出エンジンを使用します。 この保護は、SharePoint Online、OneDrive、Microsoft Teams を含むすべてのサブスクリプションに含まれています。

> [!IMPORTANT]
> 組み込みのウイルス対策機能は、ウイルスを含むのに役立ちます。 これだけで、お客様の環境がマルウェアから保護されるわけではありません。 すべてのお客様に対して、さまざまなレイヤーでマルウェア対策保護を調査および実装し、企業インフラストラクチャをセキュリティ保護するためのベスト プラクティスを適用してください。 戦略とベスト プラクティスの詳細については、「セキュリティ ロードマップ」 [を参照してください](security-roadmap.md)。

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルが SharePoint Online にアップロードされたとき

Microsoft 365 ウイルス検出エンジンは、SharePoint Online 内で非同期的に実行されます。 **すべてのファイルは、アップロード時に自動的にスキャンされません**。 ヒューリスティックは、スキャンするファイルを決定します。 ファイルにウイルスが含まれていると見つかると、そのファイルにフラグが付けられているので、再びダウンロードできません。 2018 年 4 月に、スキャンされたファイルの 25 MB の制限が削除されました。

動作は次のとおりです。

1. ユーザーがファイルを SharePoint Online にアップロードします。
2. SharePoint Online は、ファイルがスキャンの条件を満たしたかどうかを判断します。
3. ウイルス検出エンジンによってファイルがスキャンされます。
4. ウイルスが見つかった場合、ウイルス エンジンは、ウイルスに感染したことを示すプロパティをファイルに設定します。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>ブラウザーを使って感染したファイルをダウンロードしようとしても、

ファイルが感染している場合、ユーザーはブラウザーを使用して SharePoint Online からファイルをダウンロードできない。

動作は次のとおりです。

1. Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、
2. ウイルスが検出されたという警告がユーザーに表示されます。 既定では、ユーザーはファイルをダウンロードして、自分のデバイス上のウイルス対策ソフトウェアを使用してファイルのクリーンアップを試みるオプションを選択できます。

> [!NOTE]
>
> 管理者は、SharePoint Online PowerShell の [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットで *DisallowInfectedFileDownload* パラメーターを使用して、ウイルス対策警告ウィンドウでも、ユーザーがウイルスに感染したファイルをダウンロードするのを防止できます。 手順については [、「SharePoint Online PowerShell を使用して、ユーザーが悪意のあるファイルをダウンロードするのを防ぐ」を参照してください](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。
>
> *DisallowInfectedFileDownload* パラメーターを有効にしたとすぐに、検出またはブロックされたファイルへのアクセスは、ユーザーと管理者に対して完全にブロックされます。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

OneDrive 同期クライアントは、ウイルスを含むファイルをダウンロードしません。 ファイルを同期できないという通知が同期クライアントに表示されます。

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の拡張機能

Microsoft Defender for Office [365](office-365-atp.md) をサブスクリプションに含めるか、アドオンとして購入した Microsoft 365 組織では、レポートと保護を強化するために SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルを有効にできます。 詳細については [、「SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル」を参照してください](atp-for-spo-odb-and-teams.md)。

## <a name="related-articles"></a>関連記事

[Microsoft 365 のマルウェアとランサムウェアからの保護](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

SharePoint Online、OneDrive、および Microsoft Teams のウイルス対策の詳細については[](protect-against-threats.md)、「脅威からの保護」および[「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)の安全な添付ファイルを有効にする」を参照してください。
