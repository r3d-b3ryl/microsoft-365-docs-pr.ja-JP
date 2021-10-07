---
title: オンライン、SharePoint、およびOneDriveに組み込Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: ユーザーがアップロードSharePointファイル内のウイルスをオンラインで検出し、ユーザーがファイルをダウンロードまたは同期する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ddb424458e991becefb98efbad5b2a86c5f9441c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208903"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>オンライン、SharePoint、およびOneDriveに組み込Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

Microsoft 365は SharePoint、ユーザーがオンライン、OneDrive、およびファイルにアップロードするファイルをスキャンするために、一般的なOneDriveを使用Microsoft Teams。 この保護は、オンライン、オンライン、SharePoint、およびOneDrive含Microsoft Teams。

> [!IMPORTANT]
> 組み込みのウイルス対策機能は、ウイルスを含むのに役立つ方法です。 これだけで、お客様の環境がマルウェアから保護されるわけではありません。 すべてのお客様に対して、さまざまな層でマルウェア対策保護を調査および実装し、企業インフラストラクチャを保護するためのベスト プラクティスを適用してください。 戦略とベスト プラクティスの詳細については、「セキュリティ ロードマップ」 [を参照してください](security-roadmap.md)。

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染したファイルがオンラインにアップロードされた場合SharePointされますか?

ウイルスMicrosoft 365検出エンジンは、オンライン内で (ファイルのアップロードとは独立して) 非同期SharePointします。 **すべてのファイルは自動的にスキャンされません**。 ヒューリスティックは、スキャンするファイルを決定します。 ファイルにウイルスが含まれていると検出された場合、ファイルにフラグが設定されます。 2018 年 4 月に、スキャンしたファイルの 25 MB の制限が削除されました。

動作は次のとおりです。

1. ユーザーがファイルを SharePoint Online にアップロードします。
2. SharePointオンラインでは、ウイルススキャンプロセスの一環として、ファイルがスキャンの条件を満たしたかどうかを後で判断します。
3. ファイルがスキャンの条件を満たしている場合、ウイルス検出エンジンはファイルをスキャンします。
4. スキャンしたファイル内でウイルスが検出された場合、ウイルス エンジンはファイルに感染したことを示すプロパティを設定します。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>ブラウザーを使って感染したファイルをダウンロードしようとしても、

ファイルが感染している場合、ユーザーはブラウザーを使用して SharePointオンラインからファイルをダウンロードできない。

動作は次のとおりです。

1. Web ブラウザーを開き、感染したファイルを SharePoint Online からダウンロードしようとすると、
2. ユーザーには、ウイルスが検出されたという警告が表示されます。 既定では、ユーザーはファイルをダウンロードし、自分のデバイスでウイルス対策ソフトウェアを使用してファイルをクリーンアップするオプションを与えられます。

> [!NOTE]
>
> 管理者は、SharePoint Online PowerShell の [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)コマンドレットの *DisallowInfectedFileDownload* パラメーターを使用して、ウイルス対策の警告ウィンドウでも、ユーザーが感染したファイルをダウンロードすることはできません。 手順については、「ユーザーが悪意のある[ファイルをダウンロードSharePointオンライン PowerShell を使用する」を参照してください](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。
>
> *DisallowInfectedFileDownload* パラメーターを有効にしたとすぐに、検出またはブロックされたファイルへのアクセスは、ユーザーと管理者に対して完全にブロックされます。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>感染したファイルを OneDrive の同期クライアントが同期しようとするとどうなりますか?

悪意のあるファイルがマルウェアにアップロードOneDrive、マルウェアとしてマークされる前にローカル コンピューターに同期されます。 マルウェアとしてマークされた後、ユーザーはローカル コンピューターから同期されたファイルを開くことができません。

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Microsoft Defender を使用した機能の拡張Office 365

Microsoft 365 Office 365 用[Microsoft Defender](defender-for-office-365.md)をサブスクリプションに含める組織、またはアドオンとして購入した組織では、セーフ 添付ファイルを SharePoint、OneDrive、および Microsoft Teams に対して有効にして、レポートと保護を強化できます。 詳細については、「[SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)」を参照してください。

## <a name="related-articles"></a>関連記事

[マルウェアとランサムウェアのMicrosoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

SharePoint Online、OneDrive、および Microsoft Teams のウイルス対策の詳細については、「脅威から保護する」および「SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルを有効にする」を[参照してください](turn-on-mdo-for-spo-odb-and-teams.md)。 [](protect-against-threats.md)
