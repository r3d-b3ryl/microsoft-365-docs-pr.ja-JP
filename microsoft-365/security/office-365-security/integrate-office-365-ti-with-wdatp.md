---
title: Office 365 の ATP と Microsoft Defender ATP を統合する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合し、より詳細な脅威管理情報を表示します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086710"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection を使用して Office 365 Advanced Threat Protection を統合する

[Office 365 Advanced Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (OFFICE 365 atp) は、 [Microsoft Defender advanced threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (microsoft defender atp) で動作するように構成できます。

Microsoft Defender ATP を使用して Office 365 ATP を統合することにより、ユーザーのデバイスが危険にさらされている場合に、セキュリティ運用チームが迅速に監視してアクションを実行できるようになります。 たとえば、統合が有効になると、セキュリティ運用チームは、検出された電子メールメッセージによって影響を受ける可能性があるデバイス、およびそれらのデバイスが Microsoft Defender ATP で保持している最近の通知の数を表示できるようになります。 

次の図は、Microsoft Defender ATP の統合が有効になっている**デバイス**タブの外観を示しています。
  
![Microsoft Defender ATP が有効になっている場合は、アラートがあるデバイスの一覧を表示できます。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
この例では、検出された電子メールメッセージの受信者に4つのデバイスがあり、1つに通知があることがわかります。 デバイスのリンクをクリックすると、Microsoft Defender セキュリティセンター () にそのページが表示さ [https://securitycenter.windows.com](https://securitycenter.windows.com) れます。

> [!TIP]
> Microsoft Defender セキュリティセンター (Microsoft Defender ATP ポータルとも呼ばれます)**[の詳細については、こちら](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** を参照してください。
  
## <a name="requirements"></a>要件

- 組織では、Office 365 ATP Plan 2 (または Office 365 E5) と Microsoft Defender ATP を所有している必要があります。
    
- [セキュリティ/ &amp; コンプライアンスセンター](https://protection.office.com)では、全体管理者であるか、セキュリティ管理者の役割 (セキュリティ管理者など) が割り当てられている必要があります。 ([セキュリティ &amp; コンプライアンスセンターのアクセス許可を](permissions-in-the-security-and-compliance-center.md)参照)
    
- セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方の[エクスプローラー (またはリアルタイム検出)](threat-explorer.md)にアクセスできる必要があります。
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Microsoft Defender ATP を使用して Office 365 ATP を統合するには

Microsoft Defender ATP との Office 365 ATP の統合は、セキュリティ & コンプライアンスセンターと Microsoft Defender セキュリティセンターの両方を使用してセットアップされています。
  
1. グローバル管理者またはセキュリティ管理者として、に移動して、に [https://protection.office.com](https://protection.office.com) サインインします。 (これにより、Office 365 セキュリティ & コンプライアンスセンターに移動します。)
    
2. ナビゲーションウィンドウで、[**脅威管理**エクスプローラー] を選択し  >  **Explorer**ます。<br>![脅威管理メニューのエクスプローラー](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. 画面の右上にある [ **Wdatp 設定**] を選択します。
    
4. [Microsoft Defender ATP 接続] ダイアログボックスで、[ **WINDOWS ATP への接続**] をオンにします。<br>![Microsoft Defender ATP 接続](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Microsoft Defender セキュリティセンター () に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) します。

6. ナビゲーションバーで、[**設定**] を選択します。 [**全般**] で、[**高度な機能**] を選択します。

7. [ **Office 365 の脅威インテリジェンス接続**] まで下にスクロールし、接続をオンにします。<br/>![Office 365 脅威インテリジェンス接続](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>関連記事

[Office 365 の脅威の調査および応答機能](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection)
