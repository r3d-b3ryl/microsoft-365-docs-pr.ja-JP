---
title: SPO、OneDrive、Teams 用の安全な添付ファイル機能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Microsoft Defender for Office 365オンライン、SharePoint、OneDrive for Business、およびMicrosoft Teams。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 23348b0f1f1bff3a9abde8c0b6d890eb39fd898d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60180867"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SPO、OneDrive、Teams 用の安全な添付ファイル機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セーフ[microsoft Defender](whats-new-in-defender-for-office-365.md) for Office 365 の SharePoint、OneDrive、および Microsoft Teams の添付ファイルは、Microsoft 365 の一般的なウイルス検出エンジンによって既に非同期的にスキャンされているファイルに対する保護の[追加層を提供します](virus-detection-in-spo.md)。 セーフSharePoint、OneDrive、Microsoft Teamsの添付ファイルは、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別される既存のファイルを検出およびブロックするのに役立ちます。

セーフ既定ではSharePoint、OneDrive、Microsoft Teamsの添付ファイルは有効になっていません。 有効にする方法については、「添付ファイルを[有効にするセーフ」をSharePoint、OneDrive、およびMicrosoft Teams。](turn-on-mdo-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>セーフ、SharePoint、およびOneDriveの添付ファイルのMicrosoft Teams方法

SharePoint セーフ、OneDrive、Microsoft Teams の添付ファイルを有効にし、ファイルを悪意のあるファイルとして識別すると、ファイルストアとの直接統合を使用してファイルがロックされます。 次の画像は、ライブラリで検出された悪意のあるファイルの例を示しています。

![悪意のあるファイルOneDrive for Business検出されたファイルと一緒に保存されます。](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

ブロックされたファイルは、ドキュメント ライブラリと Web、モバイル、またはデスクトップ アプリケーションに引き続き表示されますが、ユーザーはファイルを開く、コピー、移動、または共有できません。 ただし、ブロックされたファイルは削除できます。

モバイル デバイスでブロックされたファイルの外観の例を次に示します。

![ブロックされたファイルをモバイル アプリOneDrive for BusinessからOneDrive削除します。](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

既定では、ユーザーはブロックされたファイルをダウンロードできます。 ブロックされたファイルをモバイル デバイスでダウンロードする方法を次に示します。

![ブロックされたファイルを OneDrive for Business。](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePointオンライン管理者は、悪意のあるファイルをダウンロードするユーザーを防ぐ可能性があります。 手順については、「ユーザーが悪意のある[ファイルをダウンロードSharePointオンライン PowerShell を使用する」を参照してください](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。

ファイルが悪意のあるファイルとして検出された場合のユーザー エクスペリエンスの詳細については[、「SharePoint Online、OneDrive、](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)または Microsoft Teams で悪意のあるファイルが見つかった場合の操作」を参照してください。

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>[添付ファイル] で検出された悪意のあるファイルセーフ、SharePoint、OneDrive、Microsoft Teams

SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルによって悪意のあるファイルとして識別されたファイルは[、microsoft Defender](view-reports-for-mdo.md) for Office 365 および Explorer (およびリアルタイム検出[)](threat-explorer.md)のレポートに表示されます。

SharePoint、OneDrive、および Microsoft Teams の セーフ 添付ファイルによってファイルが悪意のあるファイルとして識別されると、ファイルは検疫でも使用できますが、管理者だけが使用できます。 詳細については、「Defender[で検疫済みファイルを管理する」を参照Office 365。](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)

## <a name="keep-these-points-in-mind"></a>これらの点に気を付ける

- Defender for Office 365は、オンライン、オンライン、OneDrive for Business、またはSharePointのすべてのファイルをMicrosoft Teams。 この動作は仕様です。 ファイルは非同期的にスキャンされます。 このプロセスでは、共有およびゲスト アクティビティ イベントとスマート ヒューリスティックと脅威シグナルを使用して、悪意のあるファイルを識別します。

- モダン エクスペリエンスを使用SharePointサイトが構成されていることを[確認します](/sharepoint/guide-to-sharepoint-modern-experience)。 モダン Office 365クラシック ビューを使用するかどうかは、セキュリティ保護用の Defender が適用されます。ただし、ファイルがブロックされている視覚的なインジケーターは、モダン エクスペリエンスでのみ使用できます。

- セーフSharePoint、OneDrive、および Microsoft Teams の添付ファイルは、Exchange Online Protection (EOP) のスパム対策とマルウェア対策保護、および セーフ リンクと セーフ のスパム対策とマルウェア対策保護を含む、組織の全体的な脅威保護戦略の一部セーフMicrosoft Defender の添付ファイル (Office 365)。 詳細については、「脅威から[保護する」を参照Office 365。](protect-against-threats.md)
