---
title: SharePoint、OneDrive、Microsoft Teams 用の ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
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
description: SharePoint Online、OneDrive for Business、Microsoft Teams でのファイル用 Office 365 Advanced Threat Protection についての詳細情報。
ms.openlocfilehash: e536809c74abbe87e1250acda3f3922180cfae97
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446265"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) での SharePoint、OneDrive、Microsoft Teams の ATP は、[Microsoft 365 の共通のウイルス検出エンジン](virus-detection-in-spo.md) によってアップロード時に既にスキャンされているファイルに対して、追加の保護レイヤーを提供します。 SharePoint、OneDrive、および Microsoft Teams 用の ATP は、チーム サイトとドキュメント ライブラリに悪意があると特定されたファイルを検出してブロックします。

規定では、SharePoint、OneDrive、Microsoft Teams の ATP は有効になっていません。 有効にするには、[[SharePoint、OneDrive、および Microsoft Teams 用の ATP を有効にする]](turn-on-atp-for-spo-odb-and-teams.md) を参照してください。

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする方法

SharePoint、OneDrive、Microsoft Teams 用 ATP が有効になっていて、ファイルが悪意のあるものと認識されると、ファイルはファイル ストアと直接統合してロックされます。 次の画像は、ライブラリで検出された悪意のあるファイルの例を示しています。

![悪意があることが検出された OneDrive for Business のファイル](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

ブロックされたファイルは、ドキュメント ライブラリおよび Web、モバイル、もしくはデスクトップ アプリケーションにまだ表示されていますが、ファイルを開く、コピー、移動、または共有することはできません。 ただし、ブロックされたファイルは削除できます。

次に、モバイル デバイスでブロックされたファイルがどのように表示されるかという例を示します。

![OneDrive モバイル アプリで OneDrive for Business からブロックされたファイルを削除する](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

規定では、ユーザーはブロックされたファイルをダウンロードすることが可能です。 次に、モバイル デバイスで、ブロックされたファイルをダウンロードするのはどのように表示されるかを示します。

![OneDrive for Business でブロックされたファイルをダウンロードする](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online 管理者は、ユーザーが悪意のあるファイルをダウンロードできないようにすることができます。 手順については、「[SharePoint Online PowerShell を使用して悪意のあるファイルをユーザーがダウンロードできないようにする ](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)」を参照してください。

ファイルが悪意のあるものであることが検出された場合のユーザー エクスペリエンスの詳細については、「[SharePoint Online、OneDrive、または Microsoft Teams に悪意のあるファイルが見つかった場合の対処方法](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)」を参照してください。

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive、Microsoft Teams 用の ATP によって検出された悪意のあるファイルに関する情報を表示する

ATP によって悪意があると識別されたファイルは、「[Office 365 Advanced Threat Protection のレポート](view-reports-for-atp.md)」と、「[エクスプローラー (およびリアルタイム検出) ](threat-explorer.md) に表示されます。

2018 年 5 月の時点では、ファイルが ATP によって悪意のあるものと識別されると、ファイルは検疫でも利用することができます。 詳細については、「[セキュリティ/コンプライアンス センターを使用して検疫済みファイルを管理する](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)」を参照してください。

## <a name="keep-these-points-in-mind"></a>留意事項

- ATP は、SharePoint Online、OneDrive for Business、または Microsoft Teams のすべてのファイルを 1 つずつスキャンするわけではありません。 これは仕様によるものです。 ファイルは非同期でスキャンされます。 このプロセスは、スマート ヒューリスティックおよび脅威のシグナルと共に、共有とゲストのアクティビティ イベントを使用して、悪質なファイルを特定します。 

- SharePoint サイトが[モダンな環境](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)を使用するために構成されていることを確認します。 ATP 保護は、モダンな環境、またはクラシック表示のどちらかが使用されるように適用しますが、ファイルがブロックされている視覚的インジケーターは、モダンな環境でのみ使用できます。

- SharePoint、OneDrive、Microsoft Teams 用の ATP は、組織の全体的な脅威保護戦略の一部であり、Exchange Online Protection (EOP) でスパム対策やマルウェア保護対策、そしておよび Office 365 ATP の安全なリンクと安全な添付ファイルが含まれます。 詳細については、「[Office 365 で脅威から保護する](protect-against-threats.md)」をご覧ください。
