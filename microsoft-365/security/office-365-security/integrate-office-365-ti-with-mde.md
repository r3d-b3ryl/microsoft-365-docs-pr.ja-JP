---
title: Microsoft Defender for Endpoint とOffice 365 Microsoft Defender を使用する
f1.keywords:
- NOCSH
keywords: 統合, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 12/02/2021
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Microsoft Defender for Office 365 Microsoft Defender for Endpoint を使用して、デバイスやメール コンテンツに対する脅威に関する詳細な情報を取得します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef1f89a9b218e559855789d0beabad1bc947dad1
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465929"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint とOffice 365 Microsoft Defender を使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender for Office 365](defender-for-office-365.md)は、[Microsoft Defender for Endpoint で動作するように構成できます](/windows/security/threat-protection)。

Microsoft Defender for Office 365 Microsoft Defender for Endpoint を統合すると、セキュリティ運用チームがユーザーのデバイスが危険にさらされている場合に迅速に監視し、アクションを実行できます。 たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メール メッセージの影響を受ける可能性のあるデバイスと、Microsoft Defender for Endpoint のデバイスに対して生成された最近のアラートの数を確認できます。

次の図は、Microsoft Defender for **Endpoint** 統合を有効にした場合の [デバイス] タブの外観を示しています。

:::image type="content" source="../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG" alt-text="アラートを含むデバイスの一覧" lightbox="../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG":::

この例では、検出された電子メール メッセージの受信者が 4 つのデバイスを持ち、1 つはアラートを持っているのを確認できます。 デバイスのリンクをクリックすると、そのページがポータルのMicrosoft 365 Defender[されます](/microsoft-365/security/defender/microsoft-365-defender)。

> [!TIP]
> 新しいMicrosoft 365 Defenderポータルは、新しいMicrosoft Defender セキュリティ センター。 「[Microsoft Defender for Endpoint in Microsoft 365 Defender」を参照してください](../defender/microsoft-365-security-center-mde.md)。

## <a name="requirements"></a>要件

- 組織には、Microsoft Defender for Office 365 (Office 365 E5) と Microsoft Defender for Endpoint が必要です。

- 管理者にグローバル管理者またはセキュリティ管理者の役割が割り当てられている必要Microsoft 365。 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

- エクスプローラー (またはリアルタイム検出) にアクセス [できる必要があります](threat-explorer.md)。

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Office 365 Microsoft Defender for Endpoint と統合するには

Microsoft Defender for Endpoint Office 365 Microsoft Defender の統合は、Defender for Endpoint と Defender for Endpoint の両方でOffice 365。

1. ポータル () にMicrosoft 365 Defenderサインイン[https://security.microsoft.com](https://security.microsoft.com)します。

2. [メール] **グループ&エクスプローラーに移動** \> **します**。 

3. [エクスプローラー **] ページ** で、画面の右上隅にある [**MDE**] を選択設定。

3. 表示される **Microsoft Defender for Endpoint** 接続のフライアウトで、[エンドポイント用 **Microsoft Defender**![](../../media/scc-toggle-on.png) Connect]をオンにし、[閉じる] を選択 **します**。

   :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="[MDE 接続] ページ" lightbox="../../media/explorer-mdeconnection-dialognew.png":::

4. ナビゲーション ウィンドウで、[次へ] **を設定**。 [エンドポイント] **ページ設定**[エンドポイント] **を選択します。**

5. 開く **[エンドポイント] ページ** で、[高度な機能] **を選択します**。

6. [脅威インテリジェンス] **接続Office 365下に** スクロールし、オンにします (![[オンに切り替え])。](../../media/scc-toggle-on.png)

   完了したら、[基本設定の保存 **] を選択します**。

## <a name="see-also"></a>関連項目

[脅威の調査と対応機能 (Office 365](office-365-ti.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)

[Microsoft Defender for Endpoint](/windows/security/threat-protection)
