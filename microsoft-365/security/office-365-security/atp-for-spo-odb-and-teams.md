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
localization_priority: Normal
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
description: SharePoint Online、OneDrive for Business、および Microsoft Teams のファイルOffice 365 用 Microsoft Defender について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9b69d2b6f075539f411da971a314c127843b945a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917572"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SPO、OneDrive、Teams 用の安全な添付ファイル機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[Microsoft Defender for Office 365](office-365-atp.md)の SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルは[、Microsoft 365](virus-detection-in-spo.md)の一般的なウイルス検出エンジンによってアップロード時に既にスキャンされているファイルに対する保護の層を追加します。 SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルは、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別される既存のファイルを検出およびブロックするのに役立ちます。

SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルは、既定では有効になっていません。 有効にする方法については [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)の安全な添付ファイルを有効にする」を参照してください。

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルの動作

SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルが有効で、ファイルが悪意のあるファイルとして識別される場合、ファイルストアとの直接統合を使用してファイルがロックされます。 次の画像は、ライブラリで検出された悪意のあるファイルの例を示しています。

![悪意のあるファイルが検出された OneDrive for Business のファイル](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

ブロックされたファイルは、ドキュメント ライブラリと Web、モバイル、またはデスクトップ アプリケーションに引き続き表示されますが、ユーザーはファイルを開く、コピー、移動、または共有できません。 ただし、ブロックされたファイルは削除できます。

モバイル デバイスでブロックされたファイルの外観の例を次に示します。

![OneDrive モバイル アプリから OneDrive for Business からブロックされたファイルを削除する](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

既定では、ユーザーはブロックされたファイルをダウンロードできます。 ブロックされたファイルをモバイル デバイスでダウンロードする方法を次に示します。

![OneDrive for Business でブロックされたファイルをダウンロードする](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online 管理者は、悪意のあるファイルをダウンロードするユーザーを防ぐ可能性があります。 手順については、「Use SharePoint Online PowerShell を使用して、ユーザーが悪意のある [ファイルをダウンロードするのを防ぐ」を参照してください](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。

ファイルが悪意のあるファイルとして検出された場合のユーザー エクスペリエンスの詳細については [、「SharePoint Online、OneDrive、または Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)で悪意のあるファイルが見つかった場合の操作」を参照してください。

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルによって検出された悪意のあるファイルに関する情報を表示する

Office 365 の Microsoft Defender によって悪意のあるファイルとして識別されたファイルは [、microsoft Defender for Office 365](view-reports-for-atp.md) および [Explorer (](threat-explorer.md)およびリアルタイム検出) のレポートに表示されます。

2018 年 5 月現在、ファイルが Microsoft Defender によって Office 365 に対して悪意のあるファイルとして識別されると、そのファイルは検疫で使用できます。 詳細については、「Use [the Security & コンプライアンス センター」を参照してください](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)。

## <a name="keep-these-points-in-mind"></a>これらの点に気を付ける

- 365 Officeの Defender は、SharePoint Online、OneDrive for Business、または Microsoft Teams のすべてのファイルをスキャンする必要があります。 この動作は仕様です。 ファイルは非同期的にスキャンされます。 このプロセスでは、共有およびゲスト アクティビティ イベントとスマート ヒューリスティックと脅威シグナルを使用して、悪意のあるファイルを識別します。

- SharePoint サイトがモダン エクスペリエンスを使用するように構成されていることを [確認します](/sharepoint/guide-to-sharepoint-modern-experience)。 365 Officeの Defender は、モダン エクスペリエンスまたはクラシック ビューを使用するかどうかに適用されます。ただし、ファイルがブロックされている視覚的なインジケーターは、モダン エクスペリエンスでのみ使用できます。

- SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルは、Exchange Online Protection (EOP) のスパム対策とマルウェア対策保護、および Microsoft Defender for Office 365 の安全なリンクと安全な添付ファイルを含む、組織の全体的な脅威保護戦略の一部です。 詳細については、「Protect [against threats in Office 365」を参照してください](protect-against-threats.md)。