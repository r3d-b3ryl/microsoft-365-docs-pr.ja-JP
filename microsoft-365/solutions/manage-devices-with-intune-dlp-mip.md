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
ms.openlocfilehash: 76c7f613ba6a859f843550e18baa78637858be46
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2021
ms.locfileid: "61129434"
---
# <a name="step-7-implement-data-loss-prevention-dlp-with-information-protection-capabilities"></a>手順 7. 情報保護機能を備えたデータ損失防止 (DLP) を実装する.

組織がすでにデータの理解、データ機密性スキーマの開発、およびスキーマの適用に時間を費やしている場合は、データ損失防止 (DLP) ポリシーを使用して、このスキーマの要素をエンドポイントに拡張する準備ができている可能性があります。 

DLP ポリシーは、情報保護およびガバナンス チームによって作成されます。 各 DLP ポリシーは、機密情報の種類やラベルなど、データ セット内で検索する要素と、このデータを保護する方法を定義します。 

たとえば、DLP ポリシーでは、パスポート番号などの個人データを検索できます。 DLP ポリシーには、パスポート番号が組織外の人々と共有されている場合など、ポリシーがアクションを実行するようにトリガーする条件が含まれます。 ポリシーが実行するアクションも構成できます。 オプションは、単にアクションを管理者に報告することから、ユーザーに警告したり、データの共有を防止したりすることまで多岐にわたります。

DLP ポリシーは、Exchange メールや SharePoint サイトなど、ポリシーを適用する場所も指定します。 管理者が利用できる場所の 1 つはデバイスです。 デバイスが選択されている場合、ポリシーを適用するユーザーとユーザー グループを指定できます。 ポリシーから除外するユーザーとユーザー グループを指定することもできます。

情報保護およびガバナンス チームが DLP ポリシーをエンドポイントに拡張する準備ができている場合は、それらと調整してデバイスをオンボードし、ポリシーをテストおよび調整し、ユーザーをトレーニングし、結果を監視する必要があります。 

情報保護チームを使用するには、次の手順を使用します。


|手順  |説明  |
|---------|---------|
|1     |  [Microsoft 365 のエンドポイントのデータ損失防止について説明する](../compliance/endpoint-dlp-learn-about.md)。        |
|2     | デバイスを Microsoft 365 コンプライアンス ソリューションにオンボードします。 次の手順については、「[エンドポイントのデータ損失防止の使用を開始する](../compliance/endpoint-dlp-getting-started.md)」を参照してください。<br>- Windows 10 および Windows 11 のオンボーディング<br>- MacOS のオンボーディング       |
|3     |   情報保護とガバナンス チームと一緒に、ポリシーの定義、テスト、調整を行います。 これには、結果の監視が含まれます。 次のリソースを参照してください。<br>- [エンドポイントデータ損失防止の使用](../compliance/endpoint-dlp-using.md)<br>- [データ損失防止のレポートを表示する](../compliance/view-the-dlp-reports.md)      |
|     |         |
