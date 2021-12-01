---
title: 手順 7. 情報保護機能を備えたデータ損失防止 (DLP) を実装する.
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
ms.custom: ''
keywords: ''
description: ''
ms.openlocfilehash: f553d303b0086483cabc8e60a7f0ec6a427c3486
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221022"
---
# <a name="step-7-implement-data-loss-prevention-dlp-with-information-protection-capabilities"></a>手順 7. 情報保護機能を備えたデータ損失防止 (DLP) を実装する.


組織がすでにデータの理解、データ機密性スキーマの開発、およびスキーマの適用に時間を費やしている場合は、データ損失防止 (DLP) ポリシーを使用して、このスキーマの要素をエンドポイントに拡張する準備ができている可能性があります。 

Microsoft Endpoint データ損失防止 (Endpoint DLP) は現在、次の対象に適用されます。
- Windows 10、Windows 11
- MacOS

DLP ポリシーは、情報保護およびガバナンス チームによって作成されます。 各 DLP ポリシーは、機密情報の種類やラベルなど、データ セット内で検索する要素と、このデータを保護する方法を定義します。 

たとえば、DLP ポリシーでは、パスポート番号などの個人データを検索できます。 DLP ポリシーには、パスポート番号が組織外の人々と共有されている場合など、ポリシーがアクションを実行するようにトリガーする条件が含まれます。 ポリシーが実行するアクションも構成できます。 オプションは、単にアクションを管理者に報告することから、ユーザーに警告したり、データの共有を防止したりすることまで多岐にわたります。

DLP ポリシーは、Exchange メールや SharePoint サイトなど、ポリシーを適用する場所も指定します。 管理者が利用できる場所の 1 つはデバイスです。 デバイスが選択されている場合、ポリシーを適用するユーザーとユーザー グループを指定できます。 ポリシーから除外するユーザーとユーザー グループを指定することもできます。

情報保護およびガバナンス チームが DLP ポリシーをエンドポイントに拡張する準備ができている場合は、エンドポイント DLP のデバイスを有効にし、DLP ポリシーをテストおよび調整し、ユーザーをトレーニングし、結果を監視するために、それらと調整する必要があります。 

![デバイス管理者向けのエンドポイント DLP 手順](../media/devices/endpoint-dlp-steps.png#lightbox)

「[手順 2. デバイスを管理に登録する](manage-devices-with-intune-enroll.md)」と[手順 6. デデバイスを Defender for Endpoint に登録して、デバイスのリスクとセキュリティ ベースラインへのコンプライアンスを監視する](manage-devices-with-intune-monitor-risk.md)を完了した場合、デバイスはすでにエンドポイント DLP に対して有効になっています。 


情報保護チームを使用するには、次の手順を使用します。


|手順  |説明  |
|---------|---------|
|1     |  [Microsoft 365 のエンドポイントのデータ損失防止について説明する](../compliance/endpoint-dlp-learn-about.md)。        |
|2     | エンドポイント DLP のデバイスを有効にします。 デバイスを Microsoft Defender for Endpoint にオンボードした場合、デバイスはエンドポイント DLP に対して既に有効になっています。 デバイスが Defender for Endpoint にオンボードされていない場合の手順については、「[エンドポイントのデータ損失防止の開始](../compliance/endpoint-dlp-getting-started.md)」を参照してください。|
|3     |   情報保護とガバナンス チームと一緒に、ポリシーの定義、テスト、調整を行います。 これには、結果の監視が含まれます。 次のリソースを参照してください。<br>- [エンドポイントデータ損失防止の使用](../compliance/endpoint-dlp-using.md)<br>- [データ損失防止のレポートを表示する](../compliance/view-the-dlp-reports.md)      |
|     |         |