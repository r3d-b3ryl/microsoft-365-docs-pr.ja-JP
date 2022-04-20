---
title: Microsoft Defender for Endpointと共にMicrosoft Defender for Office 365を使用する
f1.keywords:
- NOCSH
keywords: 統合、Microsoft Defender、Microsoft Defender for Endpoint
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
description: Microsoft Defender for Office 365をMicrosoft Defender for Endpointと共に使用して、デバイスや電子メール コンテンツに対する脅威に関する詳細な情報を取得します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8df364538e6a799557956a8d624b0561c626e4fd
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64971112"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointと共にMicrosoft Defender for Office 365を使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender for Office 365](defender-for-office-365.md)は、[Microsoft Defender for Endpoint](/windows/security/threat-protection)を操作するように構成できます。

Microsoft Defender for Office 365とMicrosoft Defender for Endpointを統合すると、セキュリティ運用チームは、ユーザーのデバイスが危険にさらされている場合に迅速に監視し、アクションを実行するのに役立ちます。 たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メール メッセージの影響を受ける可能性のあるデバイスと、Microsoft Defender for Endpoint内のそれらのデバイスに対して生成された最近のアラートの数を確認できます。

次の図は、統合を有効Microsoft Defender for Endpoint場合の [**デバイス**] タブの外観を示しています。

:::image type="content" source="../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG" alt-text="アラートを含むデバイスの一覧" lightbox="../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG":::

この例では、検出された電子メール メッセージの受信者に 4 台のデバイスがあり、1 台にアラートがあることを確認できます。 デバイスのリンクをクリックすると、[Microsoft 365 Defender ポータル](/microsoft-365/security/defender/microsoft-365-defender)でそのページが開きます。

> [!TIP]
> Microsoft 365 Defender ポータルは、Microsoft Defender セキュリティ センターを置き換えます。 [Microsoft 365 DefenderのMicrosoft Defender for Endpointを](../defender/microsoft-365-security-center-mde.md)参照してください。

## <a name="requirements"></a>要件

- 組織には、Microsoft Defender for Office 365 (またはOffice 365 E5) とMicrosoft Defender for Endpointが必要です。

- Microsoft 365には、グローバル管理者またはセキュリティ管理者ロールが割り当てられている必要があります。 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

- [エクスプローラー (またはリアルタイム検出)](threat-explorer.md) にアクセスできる必要があります。

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Office 365とMicrosoft Defender for Endpointを統合するには

Microsoft Defender for Office 365とMicrosoft Defender for Endpointの統合は、Defender for Endpoint と Defender for Office 365 の両方で設定されます。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. **[電子メール & コラボレーション** \> エクスプローラー] に移動 **します**。

3. **エクスプローラー** ページの画面の右上隅にある **[MDE 設定**] を選択します。

3. 表示される **Microsoft Defender for Endpoint接続** ポップアップで、Microsoft Defender for Endpoint (![トグル](../../media/scc-toggle-on.png) オン) **にConnect** をオンにし、[**閉じる**] を選択します。

   :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE 接続ページ" lightbox="../../media/explorer-mdeconnection-dialognew.png":::

4. ナビゲーション ウィンドウで、**設定** を選択します。 **[設定**] ページで、[エンドポイント] を選択 **します**。

5. 開いた **[エンドポイント]** ページで、[ **高度な機能**] を選択します。

6. 下にスクロールして **脅威インテリジェンス接続Office 365** し、有効にします (![オンに切り替えます)。](../../media/scc-toggle-on.png)。

   完了したら、[ **保存] 環境設定** を選択します。

## <a name="see-also"></a>関連項目

[Office 365の脅威の調査と対応の機能](office-365-ti.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)

[Microsoft Defender for Endpoint](/windows/security/threat-protection)
