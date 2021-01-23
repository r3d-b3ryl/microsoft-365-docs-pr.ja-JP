---
title: Microsoft Defender for Endpoint Office 365 と共に Microsoft Defender を使用する
f1.keywords:
- NOCSH
keywords: 統合, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Microsoft Defender for Office 365 を Microsoft Defender for Endpoint と共に使用して、デバイスやメール コンテンツに対する脅威に関する詳細情報を取得します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24b81bb4c445c44d7c0228fa1c4440faff642816
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939334"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint Office 365 と共に Microsoft Defender を使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender for Office 365](office-365-atp.md) は、Microsoft Defender for Endpoint と一緒 [に動作するように構成できます](https://docs.microsoft.com/windows/security/threat-protection)。

Office 365 用 Microsoft Defender と Microsoft Defender for Endpoint を統合すると、セキュリティ運用チームは、ユーザーのデバイスが危険にさらされている場合に迅速に監視し、アクションを実行するのに役立ちます。 たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メール メッセージの影響を受ける可能性のあるデバイスと、それらのデバイスに対して生成された最新のアラートの数をエンドポイント用 Microsoft Defender で確認できます。

次の図は、[デバイス]タブで Microsoft Defender for Endpoint 統合が有効になっていることを示しています。

![Microsoft Defender for Endpoint が有効になっていると、アラートが表示されたデバイスの一覧が表示されます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

この例では、検出された電子メール メッセージの受信者が 4 つのデバイスを持ち、1 つがアラートを持っているのを確認できます。 デバイスのリンクをクリックすると、Microsoft Defender セキュリティ センター () でページが開きます <https://securitycenter.windows.com> 。

> [!TIP]
> **[Microsoft Defender セキュリティ センター (Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** for Endpoint ポータルとも呼ばれます) の詳細をご確認ください。

## <a name="requirements"></a>要件

- 組織には、Microsoft Defender for Office 365 (または Office 365 E5) と Microsoft Defender for Endpoint が必要です。

- セキュリティ センター コンプライアンス センターで割り当てられているセキュリティ管理者の役割 (セキュリティ管理者など) がグローバル管理者 [&必要があります](https://protection.office.com)。 (「[セキュリティ/コンプライアンス センターのアクセス&」を参照)](permissions-in-the-security-and-compliance-center.md)

- セキュリティ センター コンプライアンス センターと Microsoft Defender セキュリティ センターで、エクスプローラー (またはリアルタイムの検出 [)](threat-explorer.md) &両方にアクセスできる必要があります。

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Office 365 を Microsoft Defender for Endpoint と統合するには

Office 365 用 Microsoft Defender と Microsoft Defender for Endpoint の統合は、セキュリティ & コンプライアンス センターと Microsoft Defender セキュリティ センターの両方を使用してセットアップされます。

1. グローバル管理者またはセキュリティ管理者として、移動して <https://protection.office.com> サインインします。 (これにより、コンプライアンス センターの Office 365 セキュリティ&表示されます)。

2. ナビゲーション ウィンドウで、[脅威管理 **エクスプローラー] を** \> **選択します**。

   ![脅威の管理メニューのエクスプローラー](../../media/ThreatMgmt-Explorer-nav.png)

3. 画面の右上隅で **、[Defender for Endpoint Settings (MDE Settings] ) を選択します**。

4. [Microsoft Defender for Endpoint 接続] ダイアログ ボックスで、[Microsoft Defender for Endpoint への接続 **] をオンにします**。

   ![Microsoft Defender for Endpoint 接続](../../media/Explorer-WDATPConnection-dialog.png)

5. Microsoft Defender セキュリティ センター () に移動します <https://securitycenter.windows.com> 。

6. ナビゲーション バーで、[設定] を **選択します**。 次に、[全般] **で**[高度な機能 **] を選択します**。

7. **365** 脅威インテリジェンスOfficeまで下にスクロールし、接続を有効にしてください。

   ![Office 365 脅威インテリジェンス接続](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>関連記事

[Office 365 の脅威の調査および対応機能](office-365-ti.md)

[Microsoft Defender for Office 365](office-365-atp.md)

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)
