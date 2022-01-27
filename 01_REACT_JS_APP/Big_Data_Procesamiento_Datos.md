# Referencias
- https://docs.aws.amazon.com/es_es/pricing-calculator/latest/userguide/advanced-estimate.html
- https://aws.amazon.com/es/ec2/instance-types/#:~:text=Up%20to%2040%20Gbps%20of,and%20512%20GiB%20of%20memory
- https://aws.amazon.com/es/blogs/aws/planetary-scale-computing-9-95-pflops-position-41-on-the-top500-list/
- https://cads.iiap.res.in/tools/flopsCalc
- https://aws.amazon.com/es/ec2/instance-types/p2/
- https://www.xataka.com/basics/que-son-los-teraflops-y-que-miden-exactamente
- https://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-isa-es-4/s1-bandwidth-processing.html

# ¿Cuáles son todas las herramientas de algoritmos y herramientas de analítica específicas que requieren la aplicación de servicios de procesamiento de datos remito?

> Problemas:  Binario, Clasificación multi-clase, Regresión
Algoritmos:  máquinas de factorización,  k vecinos más próximos (k-NN) (K-Nearest Neighbors), aprendizaje lineal, XGBoost

> Problemas: Series de tiempo / Pronóstico
Algoritmos: previsión DeepAR

> Problemas Detección de anomalías: 
Algoritmos: bosque de corte aleatorio (RCF)

> Problemas: Agrupación o agrupación
Algoritmos: k-means


# ¿Cuál es el software y hardware necesario para llevar a cabo dichas actividades?

## Hardware
- Number of master EMR nodes (1), EC2 instance (c4.2xlarge), Utilization (100 %Utilized/Month)
- Number of core EMR nodes (30), EC2 instance (c4.2xlarge), Utilization (100 %Utilized/Month)

Las instancias C4 están optimizadas para cargas de trabajo de uso informático intensivo y ofrecen rendimiento alto y rentable con una buena relación rendimiento informático/precio.

## Software
Amazon EMR es la plataforma de big data en la nube líder del sector destinada al procesamiento de datos, análisis interactivo y machine learning (ML) mediante el uso de marcos de código abierto: 
- Apache Spark
- Apache Hive 
- Presto.
- Amazon Sagemaker Studio
- Amazon EMR Studio
- Amazon MWAA

## Frameworks/Lenguajes
- Jupyter Notebook
- Python
- Docker/Kubernets

## Características:

> Procesadores Intel Xeon E5-2666 v3 (Haswell) de alta frecuencia optimizados específicamente para EC2.
> Optimización para EBS predeterminada para un mayor rendimiento de almacenamiento sin costo adicional
> Rendimiento de red superior con redes mejoradas que soportan Intel 82599 VF
> Requiere Amazon VPC, Amazon EBS y AMI HVM de 64 bits

## Casos de uso

Flotas frontend de alto rendimiento, servidores web, procesamiento por lotes, análisis distribuidos, aplicaciones científicas y de ingeniería de alto rendimiento, entrega de anuncios, juegos MMO y codificación de video.


# ¿Cuál es el volumen de datos que se trabajará?

94.66 Tflops 


# ¿Qué se entregará al proyecto una vez terminada la ejecución del servicio?
> Jupyter notebooks
> Datos, descargado => Almacenados => Tranformados
> Modelos Entrenados
> Despliegue
> Evaluación y pruebas de los modelos
> Docker containers con SageMaker
> Referencia API y SDK


# Cada cuánto se recopilará y entregará información?
> Mensualmente