<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistema de Tienda de Libros</title>
    <style>
        :root {
            --orange-primary: #FF8C42;
            --orange-secondary: #FFA55C;
            --orange-light: #FFD8B8;
            --gray-dark: #333333;
            --gray-medium: #666666;
            --gray-light: #EEEEEE;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--gray-light);
            color: var(--gray-dark);
            line-height: 1.6;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            background-color: var(--orange-primary);
            color: white;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        
        h1 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 10px;
        }
        
        h2 {
            color: var(--orange-primary);
            border-bottom: 2px solid var(--orange-primary);
            padding-bottom: 10px;
            margin: 30px 0 20px;
            font-size: 1.8rem;
        }
        
        h3 {
            color: var(--gray-dark);
            margin: 20px 0 15px;
            font-size: 1.4rem;
        }
        
        .requirements-section {
            background-color: white;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        
        .requirement {
            background-color: white;
            border-left: 5px solid var(--orange-primary);
            padding: 15px;
            margin-bottom: 20px;
            border-radius: 0 5px 5px 0;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        }
        
        .requirement-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
            background-color: var(--orange-light);
            padding: 8px 15px;
            border-radius: 5px;
        }
        
        .requirement-name {
            font-weight: bold;
            color: var(--gray-dark);
        }
        
        .requirement-content {
            margin-top: 15px;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 15px 0;
            background-color: white;
        }
        
        th, td {
            padding: 12px 15px;
            text-align: left;
            border: 1px solid var(--gray-light);
        }
        
        th {
            background-color: var(--orange-secondary);
            color: white;
        }
        
        tr:nth-child(even) {
            background-color: #f9f9f9;
        }
        
        .class-diagram {
            background-color: white;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        
        .class-box {
            border: 2px solid var(--orange-primary);
            border-radius: 5px;
            margin-bottom: 30px;
            background-color: white;
        }
        
        .class-name {
            background-color: var(--orange-primary);
            color: white;
            padding: 10px;
            text-align: center;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        .class-attributes, .class-methods {
            padding: 15px;
            border-top: 1px solid var(--orange-light);
        }
        
        .class-methods {
            background-color: rgba(255, 140, 66, 0.05);
        }
        
        .enum {
            background-color: var(--gray-light);
            padding: 5px;
            border-radius: 3px;
            display: inline-block;
            margin-bottom: 5px;
            font-style: italic;
        }
        
        footer {
            text-align: center;
            margin-top: 40px;
            color: var(--gray-medium);
            padding: 20px;
        }
        
        /* Flechas y relaciones */
        .relationship {
            text-align: center;
            font-size: 2rem;
            color: var(--orange-primary);
            margin: 10px 0;
        }
        
        /* Para pantallas pequeñas */
        @media (max-width: 768px) {
            .requirement-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            h2 {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Sistema de Tienda de Libros</h1>
            <p style="text-align: center; color: white;">Documentación de requerimientos funcionales y digrama de clases</p>
        </header>
        
        <section class="requirements-section">
            <h2>Requerimientos Funcionales</h2>
            
            <div class="requirement">
                <div class="requirement-header">
                    <span class="requirement-name">R1: registrarLibroEnCatalogo</span>
                </div>
                <div class="requirement-content">
                    <p><strong>Resumen:</strong> El sistema permite verifica que no exista otro libro con el mismo ISBN, crea un nuevo libro con los datos proporcionados</p>
                    <p><strong>Entradas:</strong> ISBN, Titulo, PrecioCompra, PrecioVenta</p>
                    <p><strong>Resultado:</strong> Confirmación del registro exitoso del libro o notificación de error si el ISBN ya existe.</p>
                </div>
            </div>
            
            <div class="requirement">
                <div class="requirement-header">
                    <span class="requirement-name">R2: eliminarLibroDelCatalogo</span>
                </div>
                <div class="requirement-content">
                    <p><strong>Resumen:</strong> El sistema debe permitir eliminar un libro del catalogo</p>
                    <p><strong>Entradas:</strong> ISBN</p>
                    <p><strong>Resultado:</strong> Confirmación de la eliminación exitosa o notificación si el libro no existe</p>
                </div>
            </div>
            
            <div class="requirement">
                <div class="requirement-header">
                    <span class="requirement-name">R3: buscarLibroPorTitulo</span>
                </div>
                <div class="requirement-content">
                    <p><strong>Resumen:</strong> El sistema busca los libros</p>
                    <p><strong>Entradas:</strong> Titulo</p>
                    <p><strong>Resultado:</strong> Lista de los libros que tienen el título de búsqueda o notificación si no se encontraron coincidencias.</p>
                </div>
            </div>
            
            <div class="requirement">
                <div class="requirement-header">
                    <span class="requirement-name">R4: buscarLibroPorISBN</span>
                </div>
                <div class="requirement-content">
                    <p><strong>Resumen:</strong> El sistema busca el libro que tenga el ISBN proporcionado.</p>
                    <p><strong>Entradas:</strong> ISBN</p>
                    <p><strong>Resultado:</strong> Información del libro encontrado o notificación si no existe</p>
                </div>
            </div>
            
            <div class="requirement">
                <div class="requirement-header">
                    <span class="requirement-name">R5: abastecerEjemplaresDeUnLibro</span>
                </div>
                <div class="requirement-content">
                    <p><strong>Resumen:</strong> El sistema busca el libro por su ISBN, incrementa la cantidad actual de ejemplares, registra una transacción de tipo abastecimiento con la fecha actual y descuenta el costo total de abastecimiento del dinero en caja</p>
                    <p><strong>Entradas:</strong> ISBN, cantidadEjemplares</p>
                    <p><strong>Resultado:</strong> La cantidad de ejemplares de un libro es abastecida por el sistema.</p>
                </div>
            </div>
            
            <div class="requirement">
                <div class="requirement-header">
                    <span class="requirement-name">R6: venderEjemplaresLibro</span>
                </div>
                <div class="requirement-content">
                    <p><strong>Resumen:</strong> El sistema busca el libro por su ISBN, verifica que haya suficientes ejemplares disponibles, disminuye la cantidad actual, registra una transacción de tipo venta con la fecha actual y aumenta el dinero en caja según el precio de venta.</p>
                    <p><strong>Entradas:</strong> ISBN, cantidadEjemplares</p>
                    <p><strong>Resultado:</strong> La venta es exitosa o hay un error si no hay suficientes ejemplares.</p>
                </div>
            </div>
            
            <div class="requirement">
                <div class="requirement-header">
                    <span class="requirement-name">R7: calcularCantidadTransaccionesAbastecimientoLibro</span>
                </div>
                <div class="requirement-content">
                    <p><strong>Resumen:</strong> El sistema busca el libro por su ISBN y cuenta las transacciones de tipo abastecimiento</p>
                    <p><strong>Entradas:</strong> ISBN</p>
                    <p><strong>Resultado:</strong> El sistema retorna el número total de transacciones de abastecimiento del libro.</p>
                </div>
            </div>
            
            <div class="requirement">
                <div class="requirement-header">
                    <span class="requirement-name">R8: buscarLibroMasCaro</span>
                </div>
                <div class="requirement-content">
                    <p><strong>Resumen:</strong> El sistema compara los precios de venta de todos los libros y encuentra el más alto.</p>
                    <p><strong>Entradas:</strong> (ninguna)</p>
                    <p><strong>Resultado:</strong> La información del libro con el precio de venta más alto es arrojada por el sistema.</p>
                </div>
            </div>
            
            <div class="requirement">
                <div class="requirement-header">
                    <span class="requirement-name">R9: buscarLibroMasBarato</span>
                </div>
                <div class="requirement-content">
                    <p><strong>Resumen:</strong> El sistema compara los precios de venta de todos los libros y encuentra el de menor precio.</p>
                    <p><strong>Entradas:</strong> (ninguna)</p>
                    <p><strong>Resultado:</strong> La información del libro con el precio de venta más bajo es arrojada por el sistema.</p>
                </div>
            </div>
            
            <div class="requirement">
                <div class="requirement-header">
                    <span class="requirement-name">R10: buscarLibroMasVendido</span>
                </div>
                <div class="requirement-content">
                    <p><strong>Resumen:</strong> El sistema calcula la cantidad total de ejemplares vendidos para cada libro, sumando las cantidades de todas sus transacciones.</p>
                    <p><strong>Entradas:</strong> (ninguna)</p>
                    <p><strong>Resultado:</strong> La información del libro con la mayor cantidad de ejemplares vendidos es arrojada por el sistema.</p>
                </div>
            </div>
        </section>
        
        <section class="class-diagram">
            <h2>Diagrama de Clases</h2>
            
            <div class="class-box">
                <div class="class-name">Tienda</div>
                <div class="class-attributes">
                    <p>dineroEnCaja : float</p>
                    <p>catalogo : List &lt;Libro&gt;</p>
                </div>
                <div class="class-methods">
                    <p>Tienda(dineroInicial: float)</p>
                    <p>registrarLibro(ISBN: str, titulo: str, precioCompra: float, precioVenta: float) : voidn</p>
                    <p>eliminarLibro(ISBN: str) : void</p>
                    <p>buscarPorTitulo(titulo: str) : Libro</p>
                    <p>buscarPorISBN(ISBN: str) : Libro</p>
                    <p>abastecerLibro(ISBN: str, cantidad: int) : void</p>
                    <p>venderLibro(ISBN: str, cantidad: int) : void</p>
                    <p>contarTransaccionesAbastecimiento(ISBN: str) : int</p>
                    <p>obtenerLibroMasCostoro() : Libro</p>
                    <p>obtenerLibroMasBarato() : Libro</p>
                    <p>obtenerLibroMasVendido() : Libro</p>
                    <p>consultarSaldoEnCaja() : float</p>
                </div>
            </div>
            
            <div class="relationship">↓ contiene ↓</div>
            
            <div class="class-box">
                <div class="class-name">Libro</div>
                <div class="class-attributes">
                    <p>ISBN: str</p>
                    <p>Titulo: str</p>
                    <p>precioCompra: float</p>
                    <p>precioVenta: float</p>
                    <p>cantidadActual: int</p>
                    <p>Transacciones: List &lt;Transacción&gt;</p>
                </div>
                <div class="class-methods">
                    <p>Libro(ISBN: str, Titulo: str, precioCompra: float, precioVenta: float)</p>
                    <p>get and set</p>
                    <p>agregarTransaccion(transacion: Transaccion) : void</p>
                </div>
            </div>
            
            <div class="relationship">↓ contiene ↓</div>
            
            <div class="class-box">
                <div class="class-name">Transaccion</div>
                <div class="class-attributes">
                    <p>TipoTransaccion: Tipo</p>
                    <p>Fecha: date</p>
                    <p>Cantidad: int</p>
                </div>
                <div class="class-methods">
                    <p>Transaccion(TipoTransaccion: tipo, Fecha: date, Cantidad: int)</p>
                    <p>get and set</p>
                </div>
            </div>
            
            <div class="relationship">↓ usa ↓</div>
            
            <div class="class-box">
                <div class="class-name">
                    <span class="enum">&lt;&lt;enumeracion&gt;&gt;</span>
                    TipoTransaccion
                </div>
                <div class="class-attributes">
                    <p>VENTA</p>
                    <p>ABASTECIMIENTO</p>
                </div>
            </div>
        </section>
        
        <footer>
            <p>Sistema de Tienda de Libros - Documentación de Requerimientos</p>
        </footer>
    </div>
</body>
</html>
